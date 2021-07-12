## Template

**Шаблоны в laravel** - когда у нас есть такие части контента,
которые повторяются на каждой странице, чтобы их не повторять,
чтобы иметь возможность изменять только один документ, а не на
всех страницах, можно создать представление с данным контентом,
а потом использовать во всех документа, просто обращаясь к ней.

---

Существует 2 вида шаблонов:

- **Первые вид** - шаблоны, в которые внедряется
  контент, допустим шапка и мы используем ее на каждой странице.
- **Второй вид** - подключаемые шаблоны, когда мы берем отдельный
  блок и подключаем его в определенное место, для того чтобы облегчить
  работы с ним и представлениями в которые он внедряется.

Пример, с использованием 1 вида шаблонов:

У нас есть шапка, очень логично будет ее занести в шаблон, так
как она используется на каждой странице:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta
      name="viewport"
      content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0"
    />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <link rel="stylesheet" href="css/app.css" />
    <title>@yield('title')</title>
  </head>
  <body>
    <header class="header">@include('inc.menu')</header>
    <section class="content">
      <div class="container">@yield('content')</div>
    </section>
  </body>
</html>
```

В этой части мы определяем, куда будет внедряться контент:

```php
@yield('content')
```

Потом в другом представлении, в котором нам нужно использовать
данную шапку:

```html
@extends('layots/header') @section('title', 'Admin panel') @section('content')
<section class="add-product">
  <form
    class="add-product__form"
    action="{{ route('addTovar') }}"
    method="post"
  >
    @csrf
    <input
      class="add-product__input"
      type="text"
      name="categories_id"
      id="categories_id"
      placeholder="Categories enter"
    />
    <input
      class="add-product__input"
      type="text"
      name="name"
      id="name"
      placeholder="Name enter"
    />
    <input
      class="add-product__input"
      type="text"
      name="code"
      id="code"
      placeholder="Code enter"
    />
    <input
      class="add-product__input"
      type="text"
      name="description"
      id="description"
      placeholder="Description enter"
    />
    <input
      class="add-product__input"
      type="text"
      name="image"
      id="image"
      placeholder="Link enter on image"
    />
    <input
      class="add-product__input"
      type="text"
      name="price"
      id="price"
      placeholder="Price enter"
    />
    <input class="add-product__button" type="submit" value="Execute" />
  </form>
</section>
@endsection
```

В начале определяем, тот шаблон который мы используем:

```php
@extends('layots/header')
```

Потом определяем сам контент, так сказать секцию, которое в
зависимости от переданного аргумента в скобках подставить
данный контент в нужное место, командой `@section('content')`:

```html
@section('content')
<section class="add-product">
  <form
    class="add-product__form"
    action="{{ route('addTovar') }}"
    method="post"
  >
    @csrf
    <input
      class="add-product__input"
      type="text"
      name="categories_id"
      id="categories_id"
      placeholder="Categories enter"
    />
    <input
      class="add-product__input"
      type="text"
      name="name"
      id="name"
      placeholder="Name enter"
    />
    <input
      class="add-product__input"
      type="text"
      name="code"
      id="code"
      placeholder="Code enter"
    />
    <input
      class="add-product__input"
      type="text"
      name="description"
      id="description"
      placeholder="Description enter"
    />
    <input
      class="add-product__input"
      type="text"
      name="image"
      id="image"
      placeholder="Link enter on image"
    />
    <input
      class="add-product__input"
      type="text"
      name="price"
      id="price"
      placeholder="Price enter"
    />
    <input class="add-product__button" type="submit" value="Execute" />
  </form>
</section>
@endsection
```

Обязательно нужно не забыть закрыть секцию командной `@endsection`

---

Второй пример, с использованием 2 вида шаблонов:

У нас есть боковое меню, которое было бы неплохо занести в
отдельный файл, чтобы не засорять шапку лишним текстом и
облегчить работу с ней. Само меню:

```html
<nav class="header__inner">
  <div class="menu">
    <ul class="menu__items">
      <li class="menu__item">
        <a class="menu__link" href="{{ route('index') }}">Home</a>
      </li>
      <li class="menu__item">
        <a class="menu__link" href="{{ route('allProduct') }}">All product</a>
      </li>
      <li class="menu__item">
        <a class="menu__link" href="{{ route('categories') }}">Categories</a>
      </li>
      <li class="menu__item">
        <a class="menu__link" href="{{ route('inGarbage') }}">In garbage</a>
      </li>
      <li class="menu__item" class="menu__item-admin">
        <a class="menu__link" href="{{ route('adminPanel') }}">Admin panel</a>
      </li>
    </ul>
  </div>
</nav>
```

И потом в шапке подключаем его:

```php
@include('inc.menu')
```

inc - название папки в которой находится данное меню.

Как это выглядит в шапке:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta
      name="viewport"
      content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0"
    />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <link rel="stylesheet" href="css/app.css" />
    <title>@yield('title')</title>
  </head>
  <body>
    <header class="header">@include('inc.menu')</header>
    <section class="content">
      <div class="container">@yield('content')</div>
    </section>
  </body>
</html>
```
