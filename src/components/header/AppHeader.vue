<template>
  <div id="container">
    <div id="content">
      <img alt="App logo" src="../../assets/appLogo.png" />
      <nav>
        <a>Início</a>
        <button @click="handleUseModal">Corredores</button>
      </nav>
    </div>
    <AppRunnersModal
      v-show="isModalVisible"
      @close='handleUseModal'
      v-bind:runners='runners'
      @remove="remove"
      @register='register'
    />
  </div>
</template>

<script>
import api from '../../plugins/api';
import AppRunnersModal from './AppRunnersModal.vue';

export default {
  name: 'AppHeader',
  components: {
    AppRunnersModal,
  },
  data() {
    return {
      isModalVisible: false,
    };
  },
  props: ['runners'],
  methods: {
    handleUseModal() {
      this.isModalVisible = !this.isModalVisible;
    },
    async remove(runner) {
      await api
        .delete(`/runners/remove/${runner.id}`)
        .then(() => {
          this.$emit('reload');
        })
        .catch((error) => {
          console.log(error);
        });
    },
    async register(data) {
      await api
        .post('/runners/add/', data)
        .then(() => {
          this.$emit('reload');
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<style scoped lang="scss">
#container {
  background: #e7eaee;
  box-shadow: rgba(0, 0, 0, 0.4) 0px 10px 20px 0px;
  border-bottom: 3px solid #3a628d;

  #content {
    height: 4rem;
    max-width: 1120px;
    margin: 0 auto;
    padding: 0 1.5rem;

    display: flex;
    align-items: center;

    img {
      height: 3.2rem;
      width: auto;
    }

    nav {
      display: flex;
      height: 5rem;
      margin-left: auto;

      a {
        color: #3a628d;
        font-weight: 600;
        font-size: 16.5px;

        line-height: 5rem;
        cursor: pointer;

        &:hover {
          color: #1f3e5f;
        }

        & + button {
          margin-left: 1.2rem;
        }
      }

      button{
        color: #3a628d;
        font-weight: 600;
        font-size: 16.5px;
      }
    }
  }
}
</style>
