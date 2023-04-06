<template>
  <div>
    <Header title="Components"/>
    <NuxtLogo />
    <Footer linkTo="/sample" pageTo="Sample Page"/>
  </div>
</template>
<script>
import NuxtLogo from "~/components/NuxtLogo.vue";
import Header from "~/components/Header.vue";
import Footer from "~/components/Footer.vue";
export default {
  components: {
    Footer,
    Header,
    NuxtLogo
  }
}
</script>
