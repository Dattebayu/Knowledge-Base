### Не подключаются стили

Бывает такое, что не подключаются стили css, выводится только html. Данная проблема вызвана
неправильным путем на папку css.
Решение:

Пописываем динамический путь к папке:
```html
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <link rel="stylesheet" href="{{asset('css/app.css')}}">
    <title>@yield('title')</title>
</head>
<body>
<header class="header">
    @include('inc.menu')
</header>
<section class="content">
  <div class="container">
    @yield('content')

  </div>
</section>
<script src="{{asset('js/main.js')}}"></script>
</body>
</html>
```

Сам путь:

```html
    <link rel="stylesheet" href="{{asset('css/app.css')}}">
```