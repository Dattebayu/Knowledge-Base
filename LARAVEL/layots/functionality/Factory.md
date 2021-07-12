## Factory

**Factory в laravel** - это специальная сущность предназначенная
для заполнения таблиц тестовыми данными. Принято использовать
factory для заполнения больших обьемов данных.

---

Для того чтобы использовать фабрику, нужно в главном сиде
DatabaseSeeder указать на ее использование, а также
указать количество строчек, которые нужно создать:

```php
    public function run()
    {
        Contact::factory()->count(50)->create();
    }
```

Так же нужно создать сам фабрику с помощью помощника artisan
`php artisan make:factory Название сида + Factory`. И в этом фабрике
указываем данные, которые хотим добавить в таблицу:

```php
    public function definition()
    {
        return [
            'name' => $this->faker->name,
            'email' => $this->faker->unique()->safeEmail,
            'subject' => $this->faker->text,
            'message' => $this->faker->text,
        ];
    }
```

Таблица со всеми возможными видами вводимых данных можно
посмотреть [тут][1].

[1]: https://github.com/fzaninotto/Faker
