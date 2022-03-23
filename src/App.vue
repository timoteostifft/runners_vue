<template>
  <div id="app">
    <AppHeader/>
    <AppSearchbar/>
    <AppTestCardContainer/>
    <AppFooter/>
  </div>
</template>

<script>
/* eslint-disable */
import AppHeader from './components/AppHeader.vue';
import AppSearchbar from './components/AppSearchBar.vue';
import AppTestCardContainer from './components/AppTestCardContainer.vue';
import AppFooter from './components/AppFooter.vue'

export default {
  name: 'App',
  components: {
    AppHeader,
    AppSearchbar,
    AppTestCardContainer,
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
