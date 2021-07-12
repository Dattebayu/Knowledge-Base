## Динамические данные

---

В представлениях laravel можно использовать динамические данные,
которые будут подставляться в зависимости от значения. Для того
чтобы использовать динамические данные, нужно использовать 
следующий синтаксис `{{ данные }}`

---

Пример:

```html
@extends ('layots/header')

@section('title')
CONTACT
@endsection

@section('content')
<h1>CONTACT</h1>
<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolor, voluptatum.</p>

<form action="{{ route('adres-contact') }}" method="post">
    @csrf
    <div class="form-group">
        <label for="name">Введите имя</label>
        <input type="text" name="name" placeholder="Введите имя" id="name" class="form-control">
    </div>
    <div class="form-group">
        <label for="email">Введите почту</label>
        <input type="email" name="email" placeholder="Введите почту" id="email"  class="form-control">
    </div>
    <div class="form-group">
        <label for="subject">Тема сообщения</label>
        <input type="text" name="subject" placeholder="Введите тему сообщения" id="subject" class="form-control">
    </div>
    <div class="form-group">
        <label for="message">Сообщение</label>
        <textarea name="message" id="message" class="form-control" placeholder="Введите сообщение"></textarea>
    </div>
    <button type="submit" class="btn btn-success">Отправить</button>
</form>

@endsection
```

В данном примере в качестве динамических данных выступает ссылка на
[route][1] `<form action="{{ route('adres-contact') }}" method="post">`

[1]: ../functionality/Route.md

