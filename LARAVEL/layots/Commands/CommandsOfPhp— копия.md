## PHP

---

В представлениях laravel можно использовать встроенные в язык php команды по типу if, for,
foreach и т.д. Для того чтобы дать понять, что мы используем именно команды, а не просто 
текст, перед командами нужно добавить @ и где кончается команда, написать ее
с припиской end.

---

Пример:

```html
@extends('layots/header')

@section('title', 'Categories')

@section('content')
<section class="categories">
  <div class="categories__inner">
    @foreach($categories as $key)
    <a class="categories__inner-link" href="/{{ $key->name }}">
      <img class="categories__inner-image" src="images/categories/{{ $key->image }}" alt="{{ $key->code }}">
      <p class="categories__inner-text">{{ $key->description }}</p>
    </a>
  @endforeach
  </div>
</section>

@endsection
```

В данном примере используется цикл `@foreach` и где он заканчивается
`@endforeach`.

