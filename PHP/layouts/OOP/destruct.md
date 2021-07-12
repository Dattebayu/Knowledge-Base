## Деструктор

Деструктор - специальный метод, которые выполняется при удалении объекта(объект живет, пока над ним производятся какие-либо действия). Применяется в большинсте своем, чтобы очистить память от данных, которыми мы забили оперативную память в ходе работы с объектом. Данные метод описывается в функции вида `__destruct`:
:

```php

class MyClass {

  public $age;

  public function __construct($age) {
    $this->$age = $age;
  }
  public function __destruct() {
    echo 'Конец работы';
  }
  public function print() {
    echo $this->age + 1;
  }
}

$obj = new MyClass(18);

echo $obj->age;
echo $obj->print();

```
