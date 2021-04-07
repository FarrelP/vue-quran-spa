<template>
  <div id="app">
    <Navbar/>
    <router-view/>
    <go-top></go-top>
    <Footer/>
  </div>
</template>

<script>
import Navbar from '@/components/Navbar.vue'
import GoTop from '@inotom/vue-go-top';
import Footer from "@/components/Footer.vue"

export default {
  components : {
    Navbar,
    GoTop,
    Footer
  }
}
</script>

<style scoped>
.vue-go-top {
  width: 50px !important;
  height: 50px !important;
  background-color: rgb(40 167 69) !important;
}
</style>