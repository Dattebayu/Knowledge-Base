### Использование данных из БД в представлениях:

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