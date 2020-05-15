<template>
  <div id="app">
   
      <!-- <router-link to="/">Home</router-link> | -->
      <Navbar />
      
    <router-view/>
  </div>
</template>
<script>
import Navbar from './views/Navbar'


export default {
  name: 'App',
  components: {
    Navbar
    
  }
}
</script>

<style>

</style>
