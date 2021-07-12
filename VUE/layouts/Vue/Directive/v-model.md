### v-model

Данная директива служит для связывания данных из vue в шаблона и наоборот.

---

Пример:

В данном примере, мы связываем значение в поле input с данными из vue.

```javascript

<template>
  <div>
    <input v-model="counter" type="text" />
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

Тут мы указываем директивой то, что хотим связать данные и какую переменную именно хотим связать:

```javascript
<input v-model="counter" type="text" />
```

Тут мы указываем переменную, которую хотим использовать для [двухстороннего связывания][1]:

```javascript

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

Примечание: прочитай, что такое data можно [тут][2]

[1]: ../Definitions/Double-sided-binding.md
[2]: Components-inside-vue-template/data.md
