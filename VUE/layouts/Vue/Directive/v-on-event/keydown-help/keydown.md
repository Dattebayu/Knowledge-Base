#### v-on:keydown.enter

Это так называемые помощник, который указывает на то чтобы выполнять функцию, не по нажатию любой клавиши, а только enter

---

Пример:
В данном примере при нажатии на enter будет выполняться функция `alertMessage`, которая выведет сообщение на экран:

```javascript

<template>
  <div>
    <input v-on:keydown.enter="alertMessage" />
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
