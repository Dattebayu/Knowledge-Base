## Запуск vue внутри laravel


Хронология команд:

- `php composer.phar require laravel/ui` - подключаем библиотеку ui в проект.
- `php artisan ui vue --auth` - из библиотеки ui подключаем vue в проект.
- `npm cache clear --force` - очищаем кеш, для того чтобы подключение всех
зависимостей не вызывало ошибок.
- `npm install` - устанавливаем все зависимости.
- `npm run dev` - запускаем.
