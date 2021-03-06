## Route

**Route в laravel** - это специальные маршруты, которые определяют
путь страницы и то что будет на ней отображено. Нахождение:
_routes/web.php_.

---

Пример:

```php
Route::get('/', function () {
    return view('home');
})->name('home');
```

Задаем метод по которому будут передаваться данные, в данном случае
get:

```php
Route::get
```

После в качестве первого аргумент определяем где будет отображаться
сайт в зависимости от того, где находится пользователь, в данном
случаи если он находится в главной директории:

```php
('/',
```

И 2 аргументом мы передаем функцию, в данном случаи возвращает
представление, которое нужно отобразить:

```php
function () {
    return view('home');
}
```

Так же можно задать динамическое имя, которое потом можно использовать
в представлениях для обращения к route:

```php
)->name('home');
```

---

Пример с использованием обращения к контроллеру:

```php
Route::post('contact/submit',
  [ContactController::class, 'submit'
])->name('adres-contact');
```

Так же как и в прошлом примере определяется метод, так как этот
контроллер берет данные из формы, по этому метод post:

```php
Route::post
```

Дальше так же определяем где будет находиться пользователь:

```php
('contact/submit'
```

А потом в качестве второго аргумента, определяем контроллер.
С начало пишем его название и преписку `::class`, которая говорит,
что мы используем именно контроллер, а потом название функции,
с которой мы собираемся работать:

```php
[ContactController::class, 'submit']
```

Чтобы использовать [динамические данные][1] в представление,
используется ключевое слово, значение может быть любым:

```php
    )->name('adres-contact');
```

Так же очень важно, что была возможность вообще работать с
контроллером, нужно указать route, что мы его используем, в
самом начале:

```php
use App\Http\Controllers\MainController;
```

[1]: ../functionality/DynamicData.md
