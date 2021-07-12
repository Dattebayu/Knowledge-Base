## Controllers

**Контроллеры в laravel** - это специальная сущность, которая
осуществляет взаимодействие между представлениями и моделями.
В представлениях задается имя [route][1], который ссылается на
контроллер, в route описывается имя контроллера и названием
функции, которая в данном контроллере будет выполняться. Команды, которые
используются в [контроллерах][2].
Нахождение:
_resources/views_.

---

Примеры:

```php
<?php

namespace App\Http\Controllers;

use App\Models\Category;
use App\Models\Product;
use Illuminate\Http\Request;

class MainController extends Controller {
public function index() {
return view('index');
}

    public function allProduct() {
      $allProduct = Product::get();
      return view('allProduct', compact('allProduct'));
    }

    public function categories() {
      $categories = Category::get();
      return view('categories', compact('categories'));
    }

    public function inGarbage() {
      return view('inGarbage');
    }

    public function adminPanel() {
      return view('adminPanel');
    }

    public function selectedCategories($selectedCategories) {
      return view('selectedCategories', compact('selectedCategories'));
    }

    public function addTovar($req) {
      $product = new Product;
      $product->categories_id = $req->input('categories_id');
      $product->name = $req->input('name');
      $product->code = $req->input('code');
      $product->description = $req->input('description');
      $product->image = $req->input('image');
      $product->price = $req->input('price');

      $product->save();

      return redirect()->route('index');
    }
}
```

В данном контроллере, создается отображение
предстовления:

```php
  public function index() {
    return view('index');
  }
```

И сохранение данных в БД:

```php
    public function addTovar($req) {
      $product = new Product;
      $product->categories_id = $req->input('categories_id');
      $product->name = $req->input('name');
      $product->code = $req->input('code');
      $product->description = $req->input('description');
      $product->image = $req->input('image');
      $product->price = $req->input('price');

      $product->save();

      return redirect()->route('index');
    }
```

Описание функции и передачи в качестве аргумента
данных (`$req`), которые передаются в форме

```php
  public function addTovar($req)
```

Создание переменной, которая создает обьект класса
модели `Product`, таблицы в базе данных

Так же хочеться отметить, чтобы была возмоность
обращаться к БД, нужно иметь к модели доступ к модели
той таблицы, с которой нужно осуществить взаимодействие

```php
use App\Models\Product;
```

[1]: ../functionality/Route.md
[2]: ../Commands/CommandsForControllers.md
