# Module 3

## Валідація

### Бібліотека JOI

- інсталяція
- Визначення схем
- Використання методів валідації
- Підтримка розширень
- Кастомні повідомлення про помилки

Example

```js
import Joi from 'joi';

const createStudentSchema = Joi.object({
  name: Joi.string().min(3).max(30).required().messages({
    'string.base': 'Username should be a string',
    'string.min': 'Username should have at least {#limit} characters',
    'string.max': 'Username should have at most {#limit} characters',
    'any.required': 'Username is required',
  }),
  email: Joi.string().email().required(),
  age: Joi.number().integer().min(6).max(16).required(),
  gender: Joi.string().valid('male', 'female', 'other').required(),
  avgMark: Joi.number().min(2).max(12).required(),
  onDuty: Joi.boolean(),
});
```

### Валідація BODY

```js
import createHttpError from 'http-errors';

export const validateBody = (schema) => async (req, res, next) => {
  try {
    await schema.validateAsync(req.body, {
      abortEarly: false,
    });
    next();
  } catch (err) {
    const error = createHttpError(400, 'Bad Request', {
      errors: err.details,
    });
    next(error);
  }
};
```

Застосування

```js
import { validateBody } from '../middlewares/validateBody.js';
import { createStudentSchema } from '../validation/students.js';

/* Решта коду файла */

router.post(
  '/',
  validateBody(createStudentSchema),
  ctrlWrapper(createStudentController),
);
```

### Валідація ID

Middleware

```js
// src/middlewares/isValidId.js

import { isValidObjectId } from 'mongoose';
import createHttpError from 'http-errors';

export const isValidId = (req, res, next) => {
  const { studentId } = req.params;
  if (!isValidObjectId(studentId)) {
    throw createHttpError(400, 'Bad Request');
  }

  next();
};
```

Застосування

```js
import { isValidId } from '../middlewares/isValidId.js';

/* Решта коду файла */

router.get('/:studentId', isValidId, ctrlWrapper(getStudentByIdController));
```
