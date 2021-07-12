### Ссылки

Для того, чтобы создать ссылку на другую страницу, используя дополнение роутинг, нужно описать следующий синтаксис:

```javascript

<template>
  <ul class="sidenav app-sidenav open">
    <li
    v-for="link in links"
    :key="link.url"
    >
      <router-link
        class="waves-effect waves-orange pointer"
        :to="link.url"
      >
        {{link.title}}
      </router-link>
    </li>
  </ul>
</template>

<script>

export default {
  data: () => ({
      links: [
      {title: 'Счет', url: '/'},
      {title: 'История', url: '/history'},
      {title: 'Планирование', url: '/planning'},
      {title: 'Новая запись', url: '/record'},
      {title: 'Категории', url: '/categories'},
    ]
  })
}
</script>

```

С начало описывается шаблон ссылки:

```javascript

  <ul class="sidenav app-sidenav open">
    <li
    v-for="link in links"
    :key="link.url"
    >
      <router-link
        class="waves-effect waves-orange pointer"
        :to="link.url"
      >
        {{link.title}}
      </router-link>
    </li>
  </ul>

```

`v-for="link in links"` - обработка цикла значений с ссылками.

`:key="link.url"` - для того чтобы работал цикл создаем специальную переменную key для различия компонентов.

`:to="link.url"` - через директиву to указываем ссылку на которую должна ввести страница.

Для того чтобы работал плагин, нужно указать шаблон через `router-link`:

```javascript
<router-link
  class="waves-effect waves-orange pointer"
  :to="link.url"
>
  {{link.title}}
</router-link>
```
