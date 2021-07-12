### v-on:keydown

Данной событие срабатывает при вводе символа. То что должен выполнить интерпретатор при нажатии записывается в кавычки `v-on:keydown="какое то действие"`.

---

У данной директивы есть вспомогательные методы:

-[v-on:keydown.enter][1]

---

Пример:
В данном примере при вводе буквы у будет выполняться функция `alertMessage`, которая выведет сообщение на экран:

```javascript

<template>
  <div>
    <input v-on:keydown="alertMessage" />
  </div>
</template>

<script>
  export default {
    data() {
      return {
        counter: 1
      }
    },
    methods: {
      alertMessage() {
        alert('Message')
      }
    }
  }
</script>


```

[1]:
