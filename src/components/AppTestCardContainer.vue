<template>
  <div id="mainContainer">
    <div id="testsContainer" v-for="test in tests" :key="test.id">
      <AppTestCard v-bind:test="test" @delete="getTests" />
    </div>
  </div>
</template>

<script>
import api from '../plugins/api';
import AppTestCard from './AppTestCard.vue';

export default {
  name: 'App',
  components: {
    AppTestCard,
  },
  data() {
    return {
      tests: [],
    };
  },
  created() {
    this.getTests();
  },
  methods: {
    getTests() {
      api
        .get('/tests/listByResult')
        .then((response) => {
          this.tests = response.data;
        })
        .catch((error) => {
          // eslint-disable-next-line no-console
          console.log(error);
        });
    },
  },
};
</script>

<style scoped lang="scss">
#mainContainer {
  max-width: 840px;
  margin: 0 auto;

  padding: 0 auto;

  display: flex;
  flex-wrap: wrap;
  justify-content: center;

  @media (min-width: 768px) {
    justify-content: space-around;
  }

  #testsContainer {
    margin-right: 2rem;
    margin-left: 2rem;

    margin-top: 30px;

    // &:last-child{
    //   margin-bottom: 60px;
    // }
  }
}
</style>
