## Обьединение

Существует 4 типа обьединения таблиц:

- Покажет только те записи для которых нашлись пары `INNER JOIN`.
- Выведет все данные из первой таблицы, а если не будет найденных из 2, проставить NULL `LEFT JOIN`.
- Выведет все записи 2 таблицы, а дле тех, которых нету данных из 1, проставит NULL `RIGHT JOIN`.
- Выведет все `OUTER JOIN`.

- Обьединение двух таблиц в 1, посредством внешних ключей и команды `JOIN`;

```SQL

SELECT orders.orderNumber, people.name, people.email FROM people
INNER JOIN orders ON people.id - order.personId

```

`SELECT orders.orderNumber, people.name, people.email` - поля, которые мы хотим вывести.

`FROM people` - из какой таблицы брать данные для сравнение, чтобы подставлять значения.

`INNER JOIN orders ON people.id - order.personId` - указываем в какую таблицу мы вставляем и по какому полю идет сравнение, для подставки значений.

- Обьединение нескольких таблиц в 1, посредством внешних ключей и команды `JOIN`;

```SQL

SELECT shop.title, people.name, people.email FROM people
INNER JOIN orders ON people.id - order.personId
INNER JOIN shop ON shop.id - order.shopId

```

`SELECT orders.orderNumber, people.name, people.email` - поля, которые мы хотим вывести.

`FROM people` - из какой таблицы брать данные для сравнение, чтобы подставлять значения.

`INNER JOIN orders ON people.id - order.personId` - указываем в какую таблицу мы вставляем и по какому полю идет сравнение, для подставки значений.
