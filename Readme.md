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

---

## Робота з файловою системою

Підключаємо бібліотеку - `import path from 'node:path';`

- `process.cwd()` - поточний шлях у якому було запущенно скрипт
- `const pathToFile = path.join(pathToWorkDir, 'some_folder', 'some_file.txt');` - створення шляху до файлу
- `const res = path.parse('/home/test/file.txt')` - повертає обєкт у якому є інформація про переданий шлях

---

## Робота з файлами

Підключаємо бібліотеку - `import fs from 'fs/promises';`

- `await fs.readFile(filename, [options])` - читання файлу
- `await fs.writeFile(filename, data, [options])` - запису у файл
- `await fs.appendFile(filename, data, [options])`- додавання у файл
- `await fs.rename(oldPath, newPath)` - зміна назви файлу
- `await fs.unlink(path, callback)` - видалення файлу.

---
