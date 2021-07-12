## Как описывается class:

```php

class MyClass {

  public $age = 18;

  function print() {
    echo $this->$age + 1;
  }
}

$obj = new MyClass()

echo $obj->age;
echo $obj->print();


```

`public $age = 18;` - переменная, а если правильнее сказать свойство объекта.

`function print() {` - метод объекта, который производит какие либо операции над свойствами объекта.

`$obj = new MyClass()` - создание объекта по средствам класса `MyClass`.

`$obj->$age;` - вызов переменной объекта.

`$obj->print();` - вызов метода объекта.
