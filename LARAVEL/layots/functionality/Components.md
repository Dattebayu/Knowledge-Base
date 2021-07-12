## Компоненты

**Компоненты в laravel** - специальная возможно добавлять готовые куски кода в представления. Для того чтобы создать компонент нужно прописать в artisan `php artisan make:component название компонента`. Чтобы использовать данные компонент в другом представлении, нужно прописать тег с названием данного компонента и припиской `x-`

---

Пример.
У нас есть основной шаблон welcome и в него мы хотим вставить компонент, которые содержит в себе надпись `Hellow wrold!`. Так выглядит сам welcome:

```html
<!DOCTYPE html>
<html lang="{{ str_replace('_', '-', app()->getLocale()) }}">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Laravel</title>
    <link
      href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700&display=swap"
      rel="stylesheet"
    />
  </head>
  <body class="antialiased">
    <x-test2 />
  </body>
</html>
```

Тут мы подключаем компонент:

```html
<x-test2 />
```

Сам компонент `test` выглядит так:

```html
<div>
  <h1>Hello world!</h1>
</div>
```
