<template>
  <div id="content">
    <img id="mainImage" alt="App logo" src="../../../assets/runner.png" />
    <div id="info">
      <p>
        Data: <span>{{ test.date }}</span>
      </p>
      <p>
        Extensão: <span>{{ test.type }} km</span>
      </p>
      <p>
        Participantes: <span>{{ test.runners.length }}</span>
      </p>
    </div>
    <nav>
      <button id="removeButton" v-on:click="remove(test.id)">
        <img alt="Remove Icon" src="../../../assets/removeIcon.png" />
      </button>
      <button id="listButton" @click='handleUseModal'>
        <img alt="List Icon" src="../../../assets/listIcon.png"/>
      </button>
      <button id="addButton" @click='handleUseForm'>
        <img alt="Register Icon" src="../../../assets/addIcon.png"/>
      </button>
    </nav>

    <AppRunnerCard
      v-show='isModalVisible'
      @close='handleUseModal'
      v-bind:test="test"
      @remove='remove'
    />
    <AppRunnerForm
      v-show='isFormVisible'
      @close='handleUseForm'
      @submit='register'
      v-bind:runners='runners'
    />
  </div>
</template>

<script>
import api from '../../../plugins/api';
import AppRunnerForm from './testCard/AppRunnerForm.vue';
import AppRunnerCard from './testCard/AppRunnerCard.vue';

export default {
  name: 'AppTestCard',
  components: {
    AppRunnerCard,
    AppRunnerForm,
  },
  data() {
    return {
      isModalVisible: false,
      isFormVisible: false,
    };
  },
  props: ['test', 'runners'],
  methods: {
    handleUseModal() {
      this.isModalVisible = !this.isModalVisible;
    },
    handleUseForm() {
      this.isFormVisible = !this.isFormVisible;
    },
    async register(runnerId) {
      await api
        .post(`/tests/add/${this.test.id}/${runnerId}`)
        .then((response) => {
          console.log(response.status);
        })
        .catch((error) => {
          console.log(error);
        });
      this.$emit('reload');
    },
    async remove(runnerId) {
      await api
        .delete(`/tests/remove/${this.test.id}/${runnerId}`)
        .then((response) => {
          console.log(response.status);
        })
        .catch((error) => {
          console.log(error);
        });
      this.$emit('reload');
    },
  },
};
</script>

<style scoped lang="scss">
#content {
  width: 100%;
  height: 100%;

  display: flex;
  align-items: center;
  flex-direction: row;

  background: #e7eaee;
  border: 3px solid #3a628d;
  border-radius: 1rem;
  box-shadow: rgba(0, 0, 0, 0.4) 0px 10px 20px 0px;

  #mainImage {
    height: 100%;
    width: 5rem;

    border-radius: 12px 0 0 12px;
    border-right: 3px solid #3a628d;
  }

  #info {
    margin-top: 24px;
    margin-left: 12px;

    display: flex;
    flex-direction: column;

    p {
      color: #3a628d;
      font-weight: 500;
      height: 3rem;
      font-size: 14px;
    }
  }

  nav {
    display: flex;
    flex-direction: column;

    margin: 6px 8px 6px 10px;

    @media (min-width: 360px) {
      margin: 6px 8px 6px 30px;
    }

    button {
      height: 35px;
      width: 35px;

      border: none;
      border-radius: 1rem;

      & + button {
        margin-top: 14px;
      }

      &:nth-child(1) {
        background: #e52e4d;

        img {
          height: 18px;
          width: auto;
        }
      }

      &:nth-child(2) {
        background: #46568f;

        img {
          height: 16px;
          width: auto;
        }
      }

      &:nth-child(3) {
        background: #25bb75;

        img {
          height: 18px;
          width: auto;
        }
      }
    }
  }
}
</style>
