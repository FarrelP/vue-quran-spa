<template>
  <body>
    <script type="application/javascript" src="https://code.jquery.com/jquery-3.6.0.slim.min.js"></script>
    <script type="application/javascript" src="https://cdn.jsdelivr.net/npm/bootstrap@4.6.0/dist/js/bootstrap.min.js"></script>
    <div id="app">
      <Navbar/>
      <router-view/>
      <go-top></go-top>
      <Footer/>
    </div>
  </body>
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