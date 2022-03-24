<template>
<div id="testsContainer">
  <h5>{{tests}}</h5>
  <AppTestCard/>
</div>
</template>

<script>
import api from '../api';
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
#testsContainer{
  max-width: 840px;

  margin: 0 auto;
  padding: 0 2rem;

  display: flex;
  flex-wrap: wrap;
  justify-content: center;

  @media (min-width: 768px) {
    justify-content: space-around;
    }
}
</style>
