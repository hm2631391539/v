<template>
  <div id="app">
   <Header/>
    <router-view></router-view>
    <Footer/>
  </div>
</template>

<script>
import Header from './h-header.vue';
import Footer from './h-footer.vue';
// import Home from '../pages/Home.vue';

export default {
  name: 'App', 
  components: {
    Header,Footer
  }
}
</script>

<style>

</style>
