# Module 3

## Пагінація

- perPage - ліміт записів на сторінці. Кількість записів чи об'єктів, які повинні бути включені на кожній сторінці
- page - номер поточної сторінки, яку переглядає користувач
- totalItems - загальна кількість записів чи об'єктів у всьому наборі даних
- totalPages - загальна кількість сторінок, яка визначається за формулою Math.ceil(totalItems / perPage)
- hasPreviousPage - прапор, який вказує, чи є для поточного запиту попередня сторінка
- hasNextPage - прапор, який вказує, чи є для поточного запиту наступна сторінка

## Utils

```js
// src/utils/parsePaginationParams.js
const parseNumber = (number, defaultValue) => {
  const isString = typeof number === 'string';
  if (!isString) return defaultValue;

  const parsedNumber = parseInt(number);
  if (Number.isNaN(parsedNumber)) {
    return defaultValue;
  }

  return parsedNumber;
};
```

```js
// src/utils/parsePaginationParams.js

export const parsePaginationParams = (query) => {
  const { page, perPage } = query;

  const parsedPage = parseNumber(page, 1);
  const parsedPerPage = parseNumber(perPage, 10);

  return {
    page: parsedPage,
    perPage: parsedPerPage,
  };
};
```
