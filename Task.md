# Exercises

## Завдання 1: Читання файлу

Створи текстовий файл, що містить інформацію про декількох людей (наприклад, їхні імена та вік). Використовуючи функцію `fs.readFile`, напиши скрипт, який:

1. Зчитує вміст файлу.
2. Виводить його у термінал.

**Умови**:

- Файл повинен бути у форматі `.txt`.
- Твій код має працювати асинхронно з використанням `await`.

---

## Завдання 2: Запис у файл

Напиши скрипт, який створює новий текстовий файл і записує у нього довільний текст за допомогою функції `fs.writeFile`.

**Умови**:

- Використай асинхронну функцію.
- Якщо файл уже існує, то він повинен бути перезаписаний.

---

### Завдання 3: Додавання до файлу

Модифікуй попередній скрипт таким чином, щоб він не перезаписував файл, а додавав новий рядок до існуючого файлу за допомогою функції `fs.appendFile`.

**Умови**:

- Вміст файлу після виконання скрипта повинен містити як старі дані, так і нові рядки.

---

## Завдання 4: Перейменування файлу

Напиши скрипт, який перейменовує існуючий файл (який ти створив у попередніх завданнях) на нове ім'я, використовуючи функцію `fs.rename`.

**Умови**:

- Старе ім'я файлу має бути передано через параметр.
- Нове ім'я також задається як параметр.

---

## Завдання 5: Видалення файлу

Створи скрипт, який видаляє файл, який ти раніше перейменував, використовуючи функцію `fs.unlink`.

**Умови**:

- У випадку, якщо файл не існує, має бути виведена відповідна помилка у термінал.

---

## Додаткові вимоги:

- Для кожного завдання створи окремий npm скрипт, щоб запускати їх через термінал. Наприклад, ти можеш додати команду у розділ `"scripts"` у файлі `package.json` для кожного завдання.