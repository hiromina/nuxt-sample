<template>
  <div>
    <hr>
    <n-link :to="linkTo">{{ pageTo }}</n-link>
  </div>
</template>

<script>
export default {
  name: 'Footer',
  props: {
    linkTo: {
      type: String,
      default: '/'
    },
    pageTo: {
      type: String,
      default: 'Top'
    }
  }
}
</script>
