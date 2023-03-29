<template>
  <section class="container">
    <h1>{{ title }}</h1>
    <ul v-for="menu in menus">
      <li><n-link :to="menu.to" :class="{ 'disabled' : !menu.active }">{{ menu.name }}</n-link></li>
    </ul>
    <hr>
    <n-link to="/">{{ from }}</n-link>
  </section>
</template>

<script>
export default {
  data() {
    return {
      title: 'Sample Page',
      from: 'Top',
      menus: [
        {
          name: 'TODO List',
          to: '/sample/todo',
          active: true
        },
        {
          name: '準備中...',
          to: '/',
          active: false
        }
      ]
    }
  }
}
</script>

<style scoped>
.disabled {
  pointer-events: none;
  text-decoration: none;
}
</style>
