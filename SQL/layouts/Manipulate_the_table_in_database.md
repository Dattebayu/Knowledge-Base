## Манипулирование с таблицами в базе данных

- Создание таблицы:

```SQL

CREATE TABLE users (
  id INT NOT NULL AUTO_INCREMENT,
  name VARCHAR(30),
  bio TEXT,
  birth DATE,
  PRIMARY KEY(id)
);

```

`CREATE TABLE` - команда для создания.

`users` - название базы данных.

`id INT NOT NULL AUTO_INCREMENT,` - создает поле с названием `id` , типом данных `INT`, оно должно быть не пустым `NOT NULL`, и является авто инкрементом, что означает каждой новое такое поле прибавляется 1.

`bio TEXT,` - создает поле с названием `bio` и типом данных `TEXT`.

`PRIMARY KEY(id)` - определяет для поля его уникальность.

- Добавление полей в таблицу:

```SQL

ALTER TABLE users ADD pass VARCHAR(32);

```

`ALTER TABLE users` - команда для добавления поля в таблицу.

`pass` - название поля.

`VARCHAR(32)` - тип данных.

- Изменение полей в таблице:

```SQL

ALTER TABLE users RENAME COLUMN pass password;

```

`ALTER TABLE users RENAME COLUMN` - команда изменения название поля таблицы.

`pass password` - меняет название поля с pass на password

```SQL

ALTER TABLE users MODIFY COLUMN pass TEXT NOT NULL

```

`ALTER TABLE users MODIFY COLUMN` - команда изменения дополнительных параметров полей таблицы.

`pass TEXT NOT NULL` - меняет тип поля на TEXT и устанавливает NOT NULL.

- Удаления поля в таблице:

```SQL

ALTER TABLE users DROP pass;

```

`ALTER TABLE users DELETE COLUMN` - команда удаления поля из таблицы.

`pass` - название поля.

- Удаление таблицы:

```SQL

DROP TABLE users;

```

`DROP TABLE` - команда для удаления.

`users` - название базы данных.
