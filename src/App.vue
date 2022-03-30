<template>
  <div id="app">
    <AppHeader/>
    <AppSearchbar @select='apllyFilter'/>
    <!-- <AppTestCardContainer v-bind:listBy="listBy"/> -->
    <AppFooter/>
  </div>
</template>

<script>
/* eslint-disable */
import AppHeader from './components/header/AppHeader.vue';
import AppSearchbar from './components/main/searchbar/AppSearchBar.vue';
import AppTestCardContainer from './components/AppTestCardContainer.vue';
import AppFooter from './components/footer/AppFooter.vue'

export default {
  name: 'App',
  components: {
    AppHeader,
    AppSearchbar,
    AppTestCardContainer,
    AppFooter,
  },
  data (){
    return {
      listBy: 'result',
    };
  },
  methods: {
    apllyFilter(listBy){
      this.listBy = listBy;
      console.log(listBy);
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Poppins', sans-serif;
  min-height: 100%;
  background: #2e4c6d;

  .modal-backdrop {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: rgba(0, 0, 0, 0.25);
    display: flex;
    justify-content: center;
    align-items: center;

    .modal {
      width: 30rem;
      padding: 1.5rem;

      background: #FFFFFF;
      box-shadow: rgba(0, 0, 0, 0.6) 0px 10px 20px 0px;

      color: #3a628d;
    }
  }

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
