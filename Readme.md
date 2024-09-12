# Module-1

## Основи

- що таке NodeJs
- де його виористовують
- npm
- package.json та скрипти

---

## Створення проєкту

### Налаштування

- встановлення npm
- встановлення nodemon
- папка src та головний файл index.js

## Робота з файлами

Підключаємо бібліотеку - `import fs from 'fs/promises';`

- `await fs.readFile(filename, [options])` - чтение файла
- `await fs.writeFile(filename, data, [options])` - запись файла
- `await fs.appendFile(filename, data, [options])`- добавление в файл
- `await fs.rename(oldPath, newPath)` - переименование файла.
- `await fs.unlink(path, callback)` - удаление файла.
