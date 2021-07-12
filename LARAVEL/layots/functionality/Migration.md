## Migration

**Migration в laravel** - специальная сущность, которая при использовании
команды [artisan][1] `php artisan migrate` создает таблицу с
заданными полями и настройками, которые вписаны в миграцию. В
Миграции есть 2 основные функции `up` - которая создает
таблицу, `down` - которая удаляет таблицу, если она существует.
Так же есть возможность откатить миграцию с помощью [artisan][1]
`php artisan migrate:rollback`, или откатить на несколько шагов
`php artisan migrate:rollback --step=5`, или вернуться в самое
начало `php artisan migrate:reset`.
Расположение:
_darabase/migrations_.

---

Существует возможность создавать поля с различными
типами данных, все типы [данных][2], самые часто используемые:
`string` - строки, `integer` - целочисленные значения,
`text` - длинный текст, `float` - нецелочисленное значение.

Так же можно применять различные [настройки][3] к полям, по типу null или
nonull, автоинкремента, начальное значение

---

Пример миграции:

```php
<?php

use Illuminate\Database\Migrations\Migration;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Support\Facades\Schema;

class CreateProductsTable extends Migration
{
    /**
     * Run the migrations.
     *
     * @return void
     */
    public function up()
    {
        Schema::create('products', function (Blueprint $table) {
          $table->id();
          $table->foreignId('categories_id');
          $table->string('name');
          $table->string('code');
          $table->text('description');
          $table->string('image');
          $table->double('price')->default(0);
          $table->timestamps();
        });
    }

    /**
     * Reverse the migrations.
     *
     * @return void
     */
    public function down()
    {
        Schema::dropIfExists('products');
    }
}
```

В данной миграции создает таблица с полями id,
`name(string)`, `foreignId('categories_id')` - внешний ключ,
`string('name')`, `string('code')`, `text('description')`,
`string('image')`, `double('price')->default(0)` - начальное
значение в поле будет 0, `timestamps()`.

[1]: Artisan.md
[2]: https://laravel.com/docs/8.x/migrations#available-column-types
[3]: https://laravel.com/docs/8.x/migrations#column-modifiers
