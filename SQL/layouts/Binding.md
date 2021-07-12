## Связывание данных

Когда у нас есть 2 или более таблицы и мы хотим использовать значения одной в другой, ссылаясь через id, нужно использовать следующую конструкцию:

- Создание таблицы:

```SQL

CREATE TABLE oreders (
  id INT NOT NULL AUTO_INCREMENT,
  shopId INT,
  personId INT,
  name VARCHAR(30),
  bio TEXT,
  birth DATE,
  PRIMARY KEY(id),
  FOREIGN KEY(shopId) REFERENCES shop(id),
  FOREIGN KEY(personId) REFERENCES person(id)
);

```

`shopId INT,` - создаем переменную, которая будет содержать id из таблицы shop.

`personId INT,` - создаем переменную, которая будет содержать id из таблицы person.

`FOREIGN KEY(shopId) REFERENCES shop(id),` - указываем, что эти поля являются внешними ключами
