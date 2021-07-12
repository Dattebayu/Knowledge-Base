## Seed

**Seed в laravel** - это специальная сущность предназначенная
для заполнения таблиц тестовыми данными. Принято использовать
seed для заполнения не больших обьемов таблиц.

---

Существует главный seed, которые вызывает все остальные
DatabaseSeeder. Сиды, которые нужно исполнить нужно записывать
в методе run:

```php
    public function run()
    {
        $this->call(ContactSeeder::class);
    }
```

Так же нужно создать сам seed с помощью помощника artisan
`php artisan make:seed Название сида + Seeder`. И в этом сиде
указываем данные, которые хотим добавить в таблицу:

```php
    public function run()
    {
        DB::table('contacts')->insert([
            'name'=>Str::random(10),
            'email'=>Str::random(10).'@mail.ru',
            'subject'=>Str::random(10),
            'message'=>Str::random(10),
        ]);
    }
```

`('contacts')` - имя таблицы в которую нужно занести данные.
`'message'=>Str::random(10)` - заполняет поле message
рандомными символами в размер 10шт.
Так же не забываем подключать классы для работы метода.
