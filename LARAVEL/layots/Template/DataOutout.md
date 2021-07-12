Вывод одного сообщения из базы данных:

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

Представление, которое вызывает route с нужным контроллером и передает id:

```html
@extends ('layots/header')

@section('title')
Messages
@endsection

@section('content')
    <h1>Messages</h1>
    @foreach($data as $key)
        <div class="alert alert-info">
            <h3>{{ $key->subject }}</h3>
            <p>{{ $key->email }}</p>
            <a href="{{ route('one-contact', $key->id) }}"><button class="btn btn-warning">Детальнее</button></a>
        </div>
    @endforeach
@endsection
```

Функция из контроллера:

```php
    public function showOneMessage($id) {
        $contact = new Contact;
        return view('one-message', ['data' => $contact->find($id)]);
    }
```

Route в котором передается id и по нему в будущем будет делаться выборка:

```php
Route::get('contact/all/{id}',[
    ContactController::class, 'showOneMessage'
])->name('one-contact');
```