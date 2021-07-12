## Использование данных из vue

Для того чтобы использовать данные в шаблонах, которые были созданы во vue компоненте используется специальная структура `{{ переменная/данные }}`. Так же обязательно нужно понимать, что данную запись можно использовать только там где у нас обычный текст, но не в тегах.

---

Пример:

В данном примере мы берем переменную из объекта data выводим ее на экран:

```javascript

<template>
  <div>
    {{ counter }}
  </div>
</template>

<script>
  export default {
    data() {
      return {
        counter: 1
      }
    }
  }
</script>


```

Примечание: прочитай, что такое data можно [тут][1]

[1]: Components-inside-vue-template/data.md