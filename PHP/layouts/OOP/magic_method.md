## Магические методы

Это специальный набор методов, которые срабатывают при определенном обращение к классу/
объекту. Такие методы начинаются с `__`, например `__construct`.

- `__construct` - специальный метод, которые выполняется в самом начале при 
  создании объекта:

<details>

```php

class MyClass {

    public $age;

    public function __construct($age) {
      $this->$age = $age;
    }
    public function print() {
      echo $this->age + 1;
    }
}

$obj = new MyClass(18); // тут мы передали значение 18, которое загрузится в поле объекта `$age`.

echo $obj->age;
echo $obj->print();

```

</details>

- `__invoke` - данный метод срабатывает при обращении к объекту как к функции.

<details>

```php

class MyClass {

    public function __invoke() {
        echo 'Сработаю при вызове объекта как к функции';
    }
    
}

$obj = new MyClass(18);
$obj();

```

</details>