## Webpack

**Webpack в laravel** - специальный конструктор, благодаря которому
можно конвертировать sass/scss/postCSS файлы в обычные css,
сжимать картинки, файлы и многое другое. Так как он встроен в laravel,
нам нужно сохранять все данные в папке public, так как она является
файлом на публикацию. Нахождение:
_webpack.mix.js._.

---

Возможности:

В начале каждого webpack сборки мы должны подключить сборку:

```php
const mix = require('laravel-mix');
```

И потом использовать нужные нам компоненты:

Преобразование scss в css:

```php
mix.sass('resources/sass/app.scss', 'public/css');
```

Передает из рабочей области js файл в область на публикацию:

```php
mix.js('resources/js/app.js', 'public/js')
```

[1]: RequestsMeaning/Meaning.md
