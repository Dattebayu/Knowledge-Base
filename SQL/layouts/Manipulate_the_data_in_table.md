## Манипулирование с данными в таблице

- Чтобы явно указать в какой таблице будет происходить манипуляция, нужно перед поле указать ее название `people . id`:

```SQL

UPDATE people SET name = 'Dmitry' WHERE people . id = 3;

```

`UPDATE people SET name = Dmitry` - изменить поле name на Dmitry.

`WHERE people . id = 3;` - выполнить действие если условие id = 3 в `таблице people` будет равно 3.

- Добавление данных в поля таблицы (можно указывать не все поля, кроме тех которые явно заданы `NOT NULL`):

```SQL

INSERT INTO people (name, pass, email) VALUES ('Dmitry','1234','foo@mail.ru')

```

`INSERT INTO people` - в какую таблицу делать добавление.

`(name, pass, email)` - в какие поля(порядок не важен).

`VALUES ('Dmitry','1234','foo@mail.ru')` - какие значения, в той же последовательности, что и были перечислены поля.

- Множественное добавление данных в поля таблицы:

```SQL

INSERT INTO people (name, pass, email)
      VALUES
      ('Dmitry','1234','foo1@mail.ru'),
      ('Andrei','4321','foo2@mail.ru'),
      ('Max','1111','foo3@gmail.com');

```

`INSERT INTO people` - в какую таблицу делать добавление.

`(name, pass, email)` - в какие поля(порядок не важен).

`VALUES`
`('Dmitry','1234','foo1@mail.ru'),`
`('Andrei','4321','foo2@mail.ru'),`
`('Max','1111','foo3@gmail.com');` - через запятую указываются значения, которые нужно добавить.

- Обновление данных в 1 поле таблицы:

```SQL

UPDATE people SET name = 'Nikola' WHERE id = 5;

```

`UPDATE people SET` - команда для изменений данных в таблице.

`name` - какое поле изменить.

`= 'Nikola'` - на какое значение.

`WHERE id = 5` - означает изменить name для поля с id = 5, чтобы явно указать какой строчке нужно сделать правку.

- Обновление данных в множестве полей таблицы:

```SQL

UPDATE people SET name = 'Nikola', password = '0000' WHERE id = 5;

```

`UPDATE people SET` - команда для изменений данных в таблице.

`name, password` - какие поля изменить.

`= 'Nikola', = '0000'` - значения для полей.

`WHERE id = 5` - означает изменить name и password для поля с id = 5, чтобы явно указать какой строчке нужно сделать правку.

- Удаление полей из таблицы:

```SQL

DELETE FROM users;

```

`DELETE FROM users;` - команда, которая удалить все поля и их данные из таблицы users.

- Но есть более элегантный способ очистки таблицы, через команду `TRUNCATE`:

```SQL

TRUNCATE users;

```
