<template>
  <div>
    <p>ユーザー {{ this.$route.params.id }} のページです</p>
    <hr>
    <n-link to="/sample/users">{{ from }}</n-link>
  </div>
</template>

<script>
export default {
  data() {
    return {
      from: 'Users'
    }
  }
}
</script>
