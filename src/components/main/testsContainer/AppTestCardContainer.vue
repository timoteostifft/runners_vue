<template>
  <div id="mainContainer">
    <header>
      <h1>Listagem de <br /><span>Corridas</span></h1>
      <button type="button" @click='handleUseModal'>
        <img alt="Register Icon" src="../../../assets/addIcon.png" />
      </button>

      <AppTestForm v-show='isModalVisible' @close='handleUseModal' @submit='register'/>
    </header>
    <!-- <div id="testsContainer" v-for="test in tests" :key="test.id">
      <AppTestCard v-bind:test="test"/>
    </div> -->
  </div>
</template>

<script>
// import api from '../../../plugins/api';
// import AppTestCard from './AppTestCard.vue';
import AppTestForm from './AppTestForm.vue';

export default {
  name: 'App',
  components: {
    // AppTestCard,
    AppTestForm,
  },
  data() {
    return {
      isModalVisible: false,
    };
  },
  props: ['tests'],
  methods: {
    handleUseModal() {
      this.isModalVisible = !this.isModalVisible;
    },
    register(data) {
      console.log('Cadastro', data);
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
