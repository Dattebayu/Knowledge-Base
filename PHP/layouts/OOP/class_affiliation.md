## Принадлежность классу

`instanceof` - проверят относится ли объект к классу, проверка идет от дочернего и на повышение иерархии:

```php

class Pages {

}

Class PagesLoad extends Pages {

}

Class PagesReset extends Pages {

}

$obj = new PagesLoad;

$obj instanceof PagesLoad; // вернет true, так как объект $obj был построен на основе дочернего класса PagesLoad
$obj instanceof Pages; // вернет true, так как объект $obj был построен на основе  дочернего класса PagesLoad который является родителем для класса Pages
$obj instanceof PagesReset; // вернет false, так как не относится к классам, которые были задействованы при создании

```
