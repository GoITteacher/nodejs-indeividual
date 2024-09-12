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

- `await fs.readFile(filename, [options])` - читання файлу
- `await fs.writeFile(filename, data, [options])` - запису у файл
- `await fs.appendFile(filename, data, [options])`- додавання у файл
- `await fs.rename(oldPath, newPath)` - зміна назви файлу
- `await fs.unlink(path, callback)` - видалення файлу.
