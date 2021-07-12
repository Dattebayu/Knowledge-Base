## Статические методы и свойства

Существуют `статические` свойства и методы, когда реализовано обращение к ним без инициализирования объекта, то есть напрямую к классу:

```php

class MyClass {

  public static $age = 18;

  public static function agePrint {
    echo $this->$age;
  }

}

MyClass::$age;

MyClass::agePrint();

```

Так же можно делать обращение к статическим методами и свойствам, через объект:

```php

class MyClass {

  public static $age = 18;

  public static function agePrint {
    echo $this->$age;
  }

}

$obj = new MyClass();

$obj::$age;

$obj::agePrint();

```
