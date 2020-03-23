<template>
  <div id="app">
    <app-navbar/>
    <router-view/>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'

export default {
  name: 'app',
  components: {
    'app-navbar' : Navbar 
  }
}
</script>
<style>
</style>
