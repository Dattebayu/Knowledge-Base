## Интерфейс

Созданы для того, чтобы задавать шаблоны для классов. В них описываются методы,
которые должны будут использованы в классах, которые будет использовать данный интерфейс.
Чтобы создать интерфейс используется специальное ключевое свойство `interface`. Чтобы
указать классу на интерфейс используется специальное ключевое слово `implements`.

```php

interface NameInterface
{
   public function getInfo(); 
}

class MyClass implements NameInterface
{
    public function getInfo() // не описав данный метод, выдаст ошибку
    {
    
    }
}

```

Так же интерфейсы могут наследоваться друг от друга:

```php

interface NameInterface1
{
   public function getInfo(); 
}

interface NameInterface2  extends NameInterface1
{
    public function setInfo();
}

class MyClass implements NameInterface2
{
    public function getInfo() // не описав данный метод, выдаст ошибку
    {
    
    }
    public function setInfo()
    {
    
    }
}

```

Можно использовать несколько интерфейсов, которые будет использовать один класс:

```php

interface NameInterface1
{
   public function getInfo(); 
}

interface NameInterface2
{
    public function setInfo();
}

class MyClass implements NameInterface2, NameInterface1
{
    public function getInfo() // не описав данный метод, выдаст ошибку
    {
    
    }
    public function setInfo()
    {
    
    }
}
```