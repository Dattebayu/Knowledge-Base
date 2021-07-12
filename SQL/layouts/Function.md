## Функции

- Посчитать количество строчек:

```SQL

SELECT COUNT(id) FROM users

```

`count(id)` - считает количество строчек `id`.

- Максимальное значение:

```SQL

SELECT MAX(price) FROM users

```

`MAX(price)` - выводит максимально значение поля `price`.

- Максимальное значение:

```SQL

SELECT MIN(price) FROM users

```

`MIN(price)` - выводит минимальное значение поля `price`.

- Среднее арифметическое значение:

```SQL

SELECT AVG(price) FROM users

```

`AVG(price)` - выводит среднее арифметическое значение поля `price`.

- Сумма:

```SQL

SELECT SUM(price) FROM users

```

`SUM(price)` - вывод сумму всех полей `price`.

- Перевод всех символов в верхний регистр:

```SQL

SELECT UCASE(name) FROM users

```

`UCASE(name)` - переводит в верхний регистр данных в полях `name`.

- Перевод всех символов в нижний регистр:

```SQL

SELECT LCASE(name) FROM users

```

`LCASE(name)` - переводит в нижний регистр данных в полях `name`.
