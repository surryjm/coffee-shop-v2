<template>
  <body>
    <div id="app">
      <a href="#main-content" class="hidden">Skip to main content</a>
      <div class="container-fluid">
        <Header /> <!--HEADER COMPONENT-->
        <Nuxt />
        <Footer />  <!--FOOTER COMPONENT-->
      </div>
    </div>
  </body>
  
</template>

<script>
import Header from '~/components/Header.vue'
import Footer from '~/components/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    Footer
  }
}
</script>

<style lang="scss">

</style>
