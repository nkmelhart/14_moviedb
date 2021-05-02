<template>
  <Navbar />
  <EmptyHome v-if="isAuthenticated"/>
  <Home v-else/>
  <Footer />
</template>

<script>

 import Navbar from './components/Navbar.vue'
 import Home from './components/Home.vue'
 import Footer from './components/Footer.vue'
 import EmptyHome from './components/EmptyHome.vue'
 import { authentication } from './helpers/useFirebase'

  export default{
    name: 'App',
    components: {Navbar, Home, Footer, EmptyHome},

    setup(){
      const { isAuthenticated } = authentication()

      return { isAuthenticated }
    }
  }

</script>
