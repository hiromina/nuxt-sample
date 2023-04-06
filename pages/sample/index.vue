<template>
  <section class="container">
    <h1>{{ title }}</h1>
    <ul v-for="menu in menus">
      <li><n-link :to="menu.to" :class="{ 'disabled' : !menu.active }">{{ menu.name }}</n-link></li>
    </ul>
    <Footer />
  </section>
</template>

<script>
import Footer from "~/components/Footer.vue";

export default {
  components: {
    Footer
  },
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
          name: 'Computed',
          to: '/sample/computed',
          active: true
        },
        {
          name: 'Users',
          to: '/sample/users',
          active: true
        },
        {
          name: 'Components',
          to: '/sample/component',
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
