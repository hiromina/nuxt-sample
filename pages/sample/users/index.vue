<template>
  <div>
    <p><a href="#" @click.stop.prevent="showUser(1)">user1</a></p>
    <p><a href="#" @click.stop.prevent="showUser(2)">user2</a></p>
    <p><a href="#" @click.stop.prevent="showUser(3)">user3</a></p>
    <hr>
    <n-link to="/sample">{{ from }}</n-link>
  </div>
</template>

<script>
export default {
  data() {
    return {
      from: 'Sample Page'
    }
  },
  methods: {
    showUser(id) {
      this.$router.push('/sample/users/' + id);
    }
  }
}
</script>
