## Команды для проверки валидации

---

Существует ряд команд, которые позволяют проводить проверки
полученных данных, допустим из форм

---

Пример как используется комманды:

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

Теперь у поля name есть следующие настройки: поле обязательное/
минимум 1 символ/максимум 40.
Тут представлены самые часто используемые команды, полный список
моно посмотреть [тут][2].

- required - обязательность заполнения
- min - минимальное кол-во символов
- max - максимальное кол-во символов
- date - формат даты
- email - формат почты

[1]: ../Commands/CommandsForValidation.md
[2]: https://laravel.su/docs/8.x/validation#available-validation-rules:~:text=%D0%9D%D0%B8%D0%B6%D0%B5%20%D0%BF%D1%80%D0%B8%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%20%D1%81%D0%BF%D0%B8%D1%81%D0%BE%D0%BA%20%D0%B2%D1%81%D0%B5%D1%85%20%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D1%8B%D1%85%20%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB%20%D0%B2%D0%B0%D0%BB%D0%B8%D0%B4%D0%B0%D1%86%D0%B8%D0%B8%20%D0%B8%20%D0%B8%D1%85%20%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%B9%3A

