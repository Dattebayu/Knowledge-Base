### Методы

Если в компоненте vue нужно описать какую либо логику на выполнение каких либо операций, используется специальный объект `methods`. Если описать какие либо функции в данном объекте, то потом можно будет обратиться к нему и использовать.

---

Пример:

```javascript

<template>
  <div>
    <button v-model>
    </button>
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
        alert(this.counter)
      }
    }
  }
</script>

```
