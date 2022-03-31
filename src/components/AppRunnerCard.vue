<template>
  <div class='modal-backdrop'>
    <div class='modal'>
       <div id='header'>
        <h3>Listagem de Corredores</h3>
        <button @click="close">
          <img alt="Remove Icon" src="../assets/removeIcon.png" />
        </button>
      </div>
      <div id='container' v-for='runner in test.runners' :key='runner.id'>
        <div id='content'>
          <p>Nome: {{runner.name}}</p>
          <p></p>
          <p></p>
          <p></p>
        </div>
        <button>
          <img src="../assets/binIcon.png" alt="">
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AppRunnerForm',
  props: ['test'],
  methods: {
    close() {
      this.$emit('close');
    },
  },
};
</script>

<style scoped lang='scss'>

#container {
  display: flex;
  flex-direction: column;

  margin-top: 2rem;
  border-bottom: 1px solid #3a628d;

  & + #container{
    margin-top: 1rem;
  }
  
  button{
    margin: auto 2.5px auto auto;
    border-radius: 16px;
    background: #e52e4d;
    padding: 8px 8.5px;

    img {
      height: 14px;
      width: 12px;
    }
  }
}

</style>
