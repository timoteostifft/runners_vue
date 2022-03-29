<template>
  <div id="mainContainer">
    <header>
      <h1>Listagem de <br /><span>Corridas</span></h1>
      <button type="button" @click='handleUseModal'>
        <img alt="Register Icon" src="../assets/addIcon.png" />
      </button>

      <AppTestForm v-show='isModalVisible' @close='handleUseModal' @submit='register'/>
    </header>
    <div id="testsContainer" v-for="test in tests" :key="test.id" @add='getTests'>
      <AppTestCard v-bind:test="test" @delete="getTests"/>
    </div>
  </div>
</template>

<script>
import api from '../plugins/api';
import AppTestCard from './AppTestCard.vue';
import AppTestForm from './AppTestForm.vue';

export default {
  name: 'App',
  components: {
    AppTestCard,
    AppTestForm,
  },
  data() {
    return {
      tests: [],
      isModalVisible: false,
    };
  },
  created() {
    this.getTests();
  },
  methods: {
    async getTests() {
      await api
        .get('/tests/listByResult')
        .then((response) => {
          this.tests = response.data;
        })
        .catch((error) => {
          // eslint-disable-next-line no-console
          console.log(error);
        });
    },
    handleUseModal() {
      this.isModalVisible = !this.isModalVisible;
    },
    async register(data) {
      await api
        .post('/tests/add/', data)
        .then((response) => {
          console.log(response.status);
        })
        .catch((error) => {
          console.log(error);
        });
      this.getTests();
      this.handleUseModal();
    },
  },
};
</script>

<style scoped lang="scss">
#mainContainer {
  max-width: 840px;
  margin: 2rem auto 0;

  display: flex;
  flex-wrap: wrap;
  justify-content: center;

  @media (min-width: 768px) {
    justify-content: space-around;
  }

  header{
    padding: 0 1rem;

    width: 100%;
    display: flex;
    flex-direction: row;

    align-items: center;

    h1 {
      color: #e7eaee;

      span {
        color: #4081c7;
      }

      @media (min-width: 640px) {
        br {
          display: none;
        }
      }
    }

    button {
      height: 35px;
      width: 35px;

      margin-left: auto;

      border: none;
      border-radius: 1rem;
      background: #25bb75;

      img {
        margin: 0 auto;
        height: 18px;
        width: auto;
      }
    }
  }

  #testsContainer {
    margin-right: 2rem;
    margin-left: 2rem;

    margin-top: 30px;
  }
}
</style>
