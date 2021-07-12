## Наследование

```php

class MyClass {

  public $age;
  public function __construct($age) {
    $this->age = $age;
  }
  public function print() {
    echo $this->age + 1;
  }
}
class MiniClass extends MyClass {
    public function printAge() {
      echo $this->age;
    }
}


$obj2 = new MiniClass(20);
$obj2->printAge();

```
