### Команды, которые используются в контроллерах:

- Создание переменной, которая берет в себя данные таблицы из базы 
данных:
```php
$contact = new Contact;
```

- `input('название поля')` - берет данные из поля по определенному названию:
```php
$contact->name = $req->input('name');
```

Мы берем данные из поля name и заносим их в объект contact в поле name:

```php
$contact->name
```

- Тут мы сохраняем данные в базе данных у обьекта `$contact`:

```php
$contact->save();
```

- `redirect()->route('Имя шаблона')` - перенаправляет пользователя на 
выбранный шаблон в скобках, в примере после выполнения всех операций,
пользователь переходит в представление home:  

```php
return redirect()->route('home')
```

- `All()` - передает все данные. В данном примере передаются данные в 
  представление, для отображения или еще какого
  то взаимодействия с данными:
  
```php
  public function allData() {
    $contact = new Contact;
    return view('messages', ['data' => $contact->all()]);
  }
```

- `get()` - работает примерно так же как и all(), но он не передает
  `$_FILES`, а так же при использование all() нельзя его изменять, то есть
добавлять еще какие условия, допустим where:
  
```php
  public function categories() {
  $categories = Category::get();
  return view('categories', compact('categories'));
  }
```

 И потом в [представлениях][1], для того что использовать данные мы используем
объект $data и работаем с его значениями.

- `find('значение')` - делает выборку данных по определенному полю,
если при сравнении данные совпадают, то она его возвращает. В данном 
примере мы передаем в функцию значение id, и потом если id совпадает,
значение передается:

```php
  public function showOneMessage($id) {
  $contact = new Contact;
  return view('one-message', ['data' => $contact->find($id)]);
  }
```  
- `delete()` - удаляет данные. В данном примере, мы с начало делаем
выборку по полю id, а потом удаляем эти данные:

```php
public function deleteMessage($id) {
  Contact::find($id)->delete();
  return redirect()->route('data-contact')->with('success', 'Сообщение было удалено');
  }
```   

-

[1]: ../Ready-madeTemplates/UseDataDB.md