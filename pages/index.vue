<template>
  <section class="container">
      <h1>{{title}}</h1>
      <hr>
      <n-link to="/sample">{{menu.sample}}</n-link>
  </section>
</template>

<script>
export default {
  data() {
    return {
      title: 'TOP',
      menu: {
        sample: 'Sample Page'
      }
    }
  }
}
</script>
