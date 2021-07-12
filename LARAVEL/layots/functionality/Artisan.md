## Artisan

**Artisan в laravel** - это специальные помощник, благодаря нему
можно создавать различные компоненты, делать миграции и многое
другое, чтобы его использовать нужно в консоле в основной
директории использовать конструкцию `php artisan команда`.

---

Команды Artisan:

- `php artisan serve` - запускает локальный сервер.
- `php artisan make:` - создает различные конструкции, по типу
  миграций, моделей, контроллеров:
  - `php artisan make:model Photo` - создает [модель][1]
    с названием Photo.
  - `php artisan make:migration create_projects_table` - создает
    [миграцию][2].
    - `php artisan migrate:rollback` - возвращает миграцию.
    - `php artisan migrate:rollback --step=5` - возвращает 5 миграций
      назад.
    - `php artisan migrate:reset` - откатывает все миграции.
    - `php artisan make:model Photo -m` - создает модель
      с названием Photo и миграцию, к этой модели.
  - `php artisan make:controller UserController` - создает [контроллер][3]
    с названием UserController.
  - `php artisan make:request StoreBlogPost` - создает [реквест][4]
    с названием StoreBlogPost.
  - `php artisan make:seeder UsersTableSeeder` - создает [сид][5]
    с названием UsersTableSeeder.
    - `php artisan db:seed` - запускает [сид][5],
      которые указаны в методе run главного сида.

[1]: ../MVC/Models.md
[2]: ../functionality/Migration.md
[3]: ../MVC/Controllers.md
[4]: ../functionality/Request.md
[5]: ../functionality/Seed.md
