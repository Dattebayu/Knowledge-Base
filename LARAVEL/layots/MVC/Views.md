## Views

**Представления в laravel** - это то с чем взаимодействует
пользователь, с внедрением php. Все взаимодействия пользователя
происходят в этих представлениях и уже в зависимости от действия
пользователя, будут происходить различные действия. Нахождение:
_resources/views_.

---

В представления встроены [шаблоны][1],
так же возможность добавления
[динамических данных][2] и внедрения
всех [возможностей php][3] по типу циклов,
условий.

---

Пример:

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

В данном примере используется обработки формы:

```html
<form class="add-product__form" action="{{ route('addTovar') }}" method="post">
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
```

Для всех форм нужно использовать специальный защитный ключ `@csrf`. Так же называть
поля name и id логически правильно и одинаково.

[1]: ../functionality/Template.md
[2]: ../functionality/DynamicData.md
[3]: ../Commands/CommandsOfPhp—%20копия.md
