
Пример изменения данных, с начало идет выборка по id, а потом перезаписываются данные
по данному id: 

Форма, в которой собираются новые данные, так же в полях данной формы уже будут
вставлены нужные данных, так что перезаписывать их не прийдется:

```html
@extends ('layots/header')

@section('title')
Update message
@endsection

@section('content')
<h1>Update message</h1>
<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolor, voluptatum.</p>

    <form action="{{ route('update-contact-submit', $data->id) }}" method="post">
        @csrf
        <div class="form-group">
            <label for="name">Введите имя</label>
            <input type="text" name="name" value="{{ $data->name }}" placeholder="Введите имя" id="name" class="form-control">
        </div>
        <div class="form-group">
            <label for="email">Введите почту</label>
            <input type="email" name="email" value="{{ $data->email }}" placeholder="Введите почту" id="email"  class="form-control">
        </div>
        <div class="form-group">
            <label for="subject">Тема сообщения</label>
            <input type="text" name="subject" value="{{ $data->subject }}" placeholder="Введите тему сообщения" id="subject" class="form-control">
        </div>
        <div class="form-group">
            <label for="message">Сообщение</label>
            <textarea name="message" id="message" class="form-control" placeholder="Введите сообщение">{{ $data->message }}</textarea>
        </div>
        <button type="submit" class="btn btn-success">Update</button>
    </form>

@endsection
```

Представление с одним сообщение, с кнопкой, которая перенаправляет 
пользователя на форму для изменения данных:

`(<a href="{{ route('update-contact', $data->id) }}"><button class="btn btn-warning">Изменить</button></a>)`:

```html
@extends ('layots/header')

@section('title')
{{ $data->subject }}
@endsection

@section('content')
    <h1>{{ $data->subject }}</h1>
        <div class="alert alert-info">
            <h3>{{ $data->subject }}</h3>
            <p>{{ $data->email }}</p>
            <a href="{{ route('update-contact', $data->id) }}"><button class="btn btn-warning">Изменить</button></a>
            <a href="{{ route('delete-contact', $data->id) }}"><button class="btn btn-warning">Удалить</button></a>
            <a href="{{ route('data-contact') }}"><button class="btn btn-primary">Назад</button></a>
        </div>
@endsection

```

Функция в контроллере, которая перезаписывает данные, по определенному id, 
определяется он командой find: 

```php
    public function updateMessageSubmit($id, ContactRequest $req) {

        $contact = Contact::find($id);
        $contact->name = $req->input('name');
        $contact->email = $req->input('email');
        $contact->subject = $req->input('subject');
        $contact->message = $req->input('message');

        $contact->save();

        return redirect()->route('one-contact', $id);
    }
```

И как выглядит route данного шаблона (метод post, так идет сбор информации из
формы и нам не нужно выводить данные в шапке):

```php
    Route::post('contact/all/{id}/update',
        [ContactController::class, 'updateMessageSubmit'
    ])->name('update-contact-submit');
```