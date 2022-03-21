<template>
  <div id="app">
    <AppHeader/>
    <AppSearchbar/>
  </div>
</template>

<script>
/* eslint-disable */
import AppHeader from './components/AppHeader.vue';
import AppSearchbar from './components/AppSearchBar.vue';

export default {
  name: 'App',
  components: {
    AppHeader,
    AppSearchbar,
  },
}
</script>

<style>
#app {
  font-family: 'Poppins', sans-serif;
  height: 100vh;
  background: #2e4c6d;
}

</style>
