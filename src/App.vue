<template>
  <div id="app">
    <AppHeader v-bind:runners='runners' @reload='getRunners'/>
    <AppSearchbar @select='apllyFilter'/>
    <AppTestCardContainer
      v-bind:tests="tests"
      v-bind:runners="runners"
      @reload='getTests'/>
    <AppFooter/>
  </div>
</template>

<script>
import AppHeader from './components/header/AppHeader.vue';
import AppSearchbar from './components/main/searchbar/AppSearchBar.vue';
import AppTestCardContainer from './components/main/testsContainer/AppTestCardContainer.vue';
import AppFooter from './components/footer/AppFooter.vue';
import api from './plugins/api';

export default {
  name: 'App',
  components: {
    AppHeader,
    AppSearchbar,
    // eslint-disable-next-line vue/no-unused-components
    AppTestCardContainer,
    AppFooter,
  },
  data() {
    return {
      listBy: 'result',
      runners: [],
      tests: [],
    };
  },
  created() {
    this.getTests(this.listBy);
    this.getRunners();
  },
  methods: {
    apllyFilter(listBy) {
      this.listBy = listBy;
      this.getTests(this.listBy);
    },
    async getRunners() {
      await api
        .get('/runners/list/')
        .then((response) => {
          this.runners = response.data;
        })
        .catch((error) => {
          console.log(error);
        });
    },
    async getTests() {
      switch (this.listBy) {
        case 'result':
          await api
            .get('/tests/listByResult')
            .then((response) => {
              this.tests = response.data;
            })
            .catch((error) => {
              console.log(error);
            });
          break;
        case 'age':
          await api
            .get('/tests/listByAge')
            .then((response) => {
              this.tests = response.data;
            })
            .catch((error) => {
              console.log(error);
            });
          break;
        default:
          await api
            .get('/tests/listByResult')
            .then((response) => {
              this.tests = response.data;
            })
            .catch((error) => {
              console.log(error);
            });
          break;
      }
    },
  },
};
</script>

<style lang="scss">
#app {
  z-index: 0;
  font-family: 'Poppins', sans-serif;
  min-height: 100%;
  background: #2e4c6d;

  .modal-backdrop {
    z-index: 1;
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
      overflow: scroll;
      height: 26rem;
      width: 26rem;
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
