<template>
  <div id="container">
    <div id="content">
      <div id="searchArea">
        <img alt="App logo" src="../../../assets/searchIcon.png" />
        <form action="">
          <label for="search">
            <input type="text" id="search" name="search" placeholder="Pesquise aqui" />
          </label>
        </form>
      </div>
      <button id="filter" @click='handleUseModal'>
        <img alt="Filter Image" src="../../../assets/filterIcon.png" />
      </button>
    </div>

    <AppFilterModal v-show='isModalVisible' @close='handleUseModal' @select='select'/>
  </div>
</template>

<script>
import AppFilterModal from './AppFilterModal.vue';

export default {
  name: 'AppSearchbar',
  components: {
    AppFilterModal,
  },
  data() {
    return {
      isModalVisible: false,
    };
  },
  methods: {
    select(value) {
      this.$emit('select', value);
    },
    handleUseModal() {
      this.isModalVisible = !this.isModalVisible;
    },
  },
};
</script>

<style scoped lang="scss">
#container{
  width: 100%;
  max-width: 840px;

  display: flex;
  align-items: center;
  margin: 4rem auto 0;

  padding: 0 1rem;

  #content{
    width: 100%;

    display: flex;
    flex-direction: row;
    align-items: center;

    #searchArea{
      height: 42px;
      width: 100%;

      display: flex;
      flex-direction: row;
      align-items: center;
      margin-right: 0.5rem;

      border: 3px solid #3a628d;
      background: #e7eaee;
      border-radius: 12rem 3rem 3rem 12rem;
      box-shadow: rgba(0, 0, 0, 0.4) 0px 10px 20px 0px;

      img {
        margin-left: -2.2px;
        height: 2.5rem;
        width: auto;

        margin-right: 0.5rem;
      }

      form{
        margin: auto 0;

        input{
          font-weight: 600;
          font-size: 14.5px;

          &::placeholder {
            color: #3a628d;
            opacity: 0.85;
          }

          &:focus {
            outline: none;
          }
        }
      }
    }

    #filter{
      height: 42px;
      width: 42px;

      background: #e7eaee;
      border-radius: 10px;
      box-shadow: rgba(0, 0, 0, 0.4) 0px 10px 20px 0px;
      border: 3px solid #3a628d;

      img {
        height: 50%;
        width: auto;
      }
    }
  }
}
</style>
