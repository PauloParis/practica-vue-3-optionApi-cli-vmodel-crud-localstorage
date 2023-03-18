<template>
  <Navbar></Navbar>

  <div class="container">
    <RouterView />
  </div>
  
</template>

<script>
import { mapActions } from 'vuex';
import Navbar from './components/Navbar.vue';


export default {
  components: {
    Navbar
  },
  methods: {
    ...mapActions(['cargarLocalStorage'])
  },
  created(){
    this.cargarLocalStorage()
  }
}

</script>

<style scoped>

</style>
