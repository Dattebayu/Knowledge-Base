## Роутинг внутри vue

Для начало хотел бы отметить, чтобы использовать роутинг, нужно будет в настройках при создании проекта включить данную функцию, для того чтобы сгенерировать соответствующие файлы.

---

Создание [ссылок][1], для перехода по роутам

---

Пример:

В данном примере будет реализован роутинг с использование 2 шаблонов. **Первый шаблон** просто с серым фоном, для регистрации и логина. **Второй шаблон** состоит из навигационной меню и сайд бара для всех остальных шаблонов.

Начнем с главного файла, куда компилица все шаблоны это `App.vue`, он выглядит следующим образом:

```javascript

<template>
  <div>
    <component :is="layout">
      <router-view />
    </component>
  </div>
</template>

<script>
import EmptyLayout from '@/layouts/EmptyLayouts'
import MainLayout from '@/layouts/MainLayouts'
export default {
  computed: {
    layout() {
      return (this.$route.meta.layout || 'empty') + '-layout'
    }
  },
  components : {
    EmptyLayout,
    MainLayout
  }
}
</script>


<style lang="scss">
@import '~materialize-css/dist/css/materialize.min.css';
@import 'assets/index.css';
</style>


```

Начнем по порядку, нам нужно динамически подставлять нужный нам layouts и сам плагин роутинга:

```javascript

<component :is="layout">
  <router-view />
</component>

```

Потом мы подключаем файлы с layouts в которые подставляются шаблоны. Создаем объект `computed` в который передаем объект для определения layouts. И потом описываем сами компоненты через `components`:

```javascript
import EmptyLayout from '@/layouts/EmptyLayouts';
import MainLayout from '@/layouts/MainLayouts';
export default {
  computed: {
    layout() {
      return (this.$route.meta.layout || 'empty') + '-layout';
    },
  },
  components: {
    EmptyLayout,
    MainLayout,
  },
};
```

Теперь в папке `Route` файле `index.js` описываем всех пути к шаблонам:

```javascript
import { createRouter, createWebHistory } from 'vue-router';
import Home from '../views/Home.vue';

const routes = [
  {
    path: '/',
    name: 'Home',
    component: Home,
  },
  {
    path: '/login',
    name: 'login',
    meta: { layout: 'empty' },
    component: () => import('../views/Login.vue'),
  },
  {
    path: '/register',
    name: 'register',
    meta: { layout: 'empty' },
    component: () => import('../views/Register.vue'),
  },
  {
    path: '/categories',
    name: 'categories',
    meta: { layout: 'main' },
    component: () => import('../views/Categories.vue'),
  },
  {
    path: '/detail-record',
    name: 'detail-record',
    meta: { layout: 'main' },
    component: () => import('../views/Detail-Record.vue'),
  },
  {
    path: '/history',
    name: 'history',
    meta: { layout: 'main' },
    component: () => import('../views/History.vue'),
  },
  {
    path: '/home',
    name: 'home',
    meta: { layout: 'main' },
    component: () => import('../views/Home.vue'),
  },
  {
    path: '/planning',
    name: 'planning',
    meta: { layout: 'main' },
    component: () => import('../views/Planning.vue'),
  },
  {
    path: '/profile',
    name: 'profile',
    meta: { layout: 'main' },
    component: () => import('../views/Profile.vue'),
  },
  {
    path: '/record',
    name: 'record',
    meta: { layout: 'main' },
    component: () => import('../views/Record.vue'),
  },
];

const router = createRouter({
  history: createWebHistory(process.env.BASE_URL),
  routes,
});

export default router;
```

Типичный шаблон(все шаблоны выглядят примерно одинакового):

```javascript

<template>
<form class="card auth-card">
  <div class="card-content">
    <span class="card-title">Домашняя бухгалтерия</span>
    <div class="input-field">
      <input
          id="email"
          type="text"
      >
      <label for="email">Email</label>
      <small class="helper-text invalid">Email</small>
    </div>
    <div class="input-field">
      <input
          id="password"
          type="password"
          class="validate"
      >
      <label for="password">Пароль</label>
      <small class="helper-text invalid">Password</small>
    </div>
    <div class="input-field">
      <input
          id="name"
          type="text"
          class="validate"
      >
      <label for="name">Имя</label>
      <small class="helper-text invalid">Name</small>
    </div>
    <p>
      <label>
        <input type="checkbox" />
        <span>С правилами согласен</span>
      </label>
    </p>
  </div>
  <div class="card-action">
    <div>
      <button
          class="btn waves-effect waves-light auth-submit"
          type="submit"
      >
        Зарегистрироваться
        <i class="material-icons right">send</i>
      </button>
    </div>

    <p class="center">
      Уже есть аккаунт?
      <a href="/">Войти!</a>
    </p>
  </div>
</form>
</template>

```

Ну и сам шаблон в который подставляются страницы:

```javascript
<template>
  <div class="grey darken-1 empty-layout">
    <router-view />
  </div>
</template>
```

[1]: Route/Route-link.md
