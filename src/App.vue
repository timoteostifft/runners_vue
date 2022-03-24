<template>
  <div id="app">
    <AppHeader/>
    <AppSearchbar/>
    <AppListTitle/>
    <AppTestCardContainer/>
    <AppFooter/>
  </div>
</template>

<script>
/* eslint-disable */
import AppHeader from './components/AppHeader.vue';
import AppSearchbar from './components/AppSearchBar.vue';
import AppListTitle from './components/AppListTitlte.vue'
import AppTestCardContainer from './components/AppTestCardContainer.vue';
import AppFooter from './components/AppFooter.vue'

export default {
  name: 'App',
  components: {
    AppHeader,
    AppSearchbar,
    AppListTitle,
    AppTestCardContainer,
    AppFooter,
  },
}
</script>

<style lang="scss">
#app {
  font-family: 'Poppins', sans-serif;
  height: 100%;
  background: #2e4c6d;

  button{
    cursor: pointer;

    display: flex;
    align-items: center;
    justify-content: center;

    transition: filter 0.5s;

    &:hover{
      filter: brightness(0.8);
    }
  }
}
</style>
