<template>
  <div id="app">
    <AppHeader/>
    <AppSearchbar/>
    <AppTestCard/>
    <AppTestCard/>
    <AppTestCard/>
    <AppTestCard/>
    <AppTestCard/>
    <AppFooter/>
  </div>
</template>

<script>
/* eslint-disable */
import AppHeader from './components/AppHeader.vue';
import AppSearchbar from './components/AppSearchBar.vue';
import AppTestCard from './components/AppTestCard.vue';
import AppFooter from './components/AppFooter.vue'

export default {
  name: 'App',
  components: {
    AppHeader,
    AppSearchbar,
    AppTestCard,
    AppFooter,
  },
}
</script>

<style>
#app {
  font-family: 'Poppins', sans-serif;
  height: 100%;
  background: #2e4c6d;
}
</style>
