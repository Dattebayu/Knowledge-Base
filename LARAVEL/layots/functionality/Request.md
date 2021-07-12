## Request

**Request в laravel** - отдельная сущность в которой можно
производить валидацию данных. Существует ряд [различных
видов проверок][1], таких как максимальное/минимальное
значение, проверка на заполненность поле и другие. Так же
существует возможность прописывать сообщения при возникновении
ошибок.Нахождение:
_app/Http/Requests_.

---

Пример:

```php
<?php

namespace App\Http\Requests;

use Illuminate\Foundation\Http\FormRequest;

class ContactRequest extends FormRequest
{
    /**
     * Determine if the user is authorized to make this request.
     *
     * @return bool
     */
    public function authorize()
    {
        return true;
    }

    /**
     * Get the validation rules that apply to the request.
     *
     * @return array
     */
    public function rules()
    {
        return [
            'name' => 'required|min:1|max:40',
            'email' => 'required|email|min:5|max:30',
            'message' => 'required|min:10|max:2000',
            'subject' => 'required'
        ];
    }

    public function messages()
    {
        return [
          'name.required' => 'Поле имя обязательное',
          'email.required' => 'Поле почта обязательное',
          'message.required' => 'Поле сообщение обязательное',
          'name.min' => 'Имя должно быть больше 5 символов',
          'name.max' => 'Имя не должно быть больше 40 символов',
          'email.email' => 'Введите корректную почту',
          'email.min' => 'Почта должна быть больше 5 символов',
          'email.max' => 'Почта не должна быть больше 30 символов',
          'message.min' => 'Сообщение должно быть больше 10 символов',
          'message.max' => 'Сообщение не должно быть больше 2000 символов',
          'subject.required' => 'Поле тема сообщения не должно быть пустым'
        ];
    }
}
```

В функции `rules` определяются поля по которым будет
производиться валидации и по каким параметрам:

```php

    public function rules()
    {
        return [
            'name' => 'required|min:1|max:40',
            'email' => 'required|email|min:5|max:30',
            'message' => 'required|min:10|max:2000',
            'subject' => 'required'
        ];
    }
```

И также в функции `messages` можно прописать сообщения, которые
будут выскакивать при возникновении той или иной ошибки:

```php
    public function messages()
    {
        return [
          'name.required' => 'Поле имя обязательное',
          'email.required' => 'Поле почта обязательное',
          'message.required' => 'Поле сообщение обязательное',
          'name.min' => 'Имя должно быть больше 5 символов',
          'name.max' => 'Имя не должно быть больше 40 символов',
          'email.email' => 'Введите корректную почту',
          'email.min' => 'Почта должна быть больше 5 символов',
          'email.max' => 'Почта не должна быть больше 30 символов',
          'message.min' => 'Сообщение должно быть больше 10 символов',
          'message.max' => 'Сообщение не должно быть больше 2000 символов',
          'subject.required' => 'Поле тема сообщения не должно быть пустым'
        ];
    }
```

Ну и конечно, чтобы контроллер смог использовать данный Request,
ему нужно указать на него:

```php
<?php

namespace App\Http\Controllers;

use Illuminate\Http\Request;
use App\Http\Requests\ContactRequest; - `Указатель`
use App\Models\Contact;

class ContactController extends Controller
```

[1]: ../Commands/CommandsForValidation.md
