<template>
  <div id="app">
    <AppHeader/>
    <AppSearchbar/>
    <AppTestCard/>
  </div>
</template>

<script>
/* eslint-disable */
import AppHeader from './components/AppHeader.vue';
import AppSearchbar from './components/AppSearchBar.vue';
import AppTestCard from './components/AppTestCard.vue';

export default {
  name: 'App',
  components: {
    AppHeader,
    AppSearchbar,
    AppTestCard
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
