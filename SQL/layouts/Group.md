## Группировка данных

- Группировка:

```SQL

SELECT price, COUNT(price) FROM shop GROUP BY price

```

`SELECT price, count(price)` - вывод данные цены и и считаем количество таких полей.

`GROUP BY price` - группируем одинаковые записи в поле price.

- Условия в группировке:

```SQL

SELECT price, COUNT(price) FROM shop GROUP BY price HAVING COUNT(price) > 1

```

`HAVING COUNT(price) > 1` - если у нас используется группировка, то вместо WHERE используется условие через оператор `HAVING` .
