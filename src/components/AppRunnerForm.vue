<template>
  <div class="modal-backdrop">
    <div class="modal">
      <div id='header'>
        <h3>Cadastro de Corredor</h3>
        <button @click="close">
          <img alt="Remove Icon" src="../assets/removeIcon.png" />
        </button>
      </div>

      <div id="body">
        <div id='runnersContainer' v-for="runner in runners" :key="runner.id">
          <div id='content'>
            {{runner}}
          </div>
          <button>+</button>
        </div>
      </div>

      <div id="footer">
        <button @click="close">
          CANCELAR
        </button>
        <button @click='register'>
          CADASTRAR
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AppRunnerForm',
  props: ['runners'],
  methods: {
    close() {
      this.$emit('close');
    },
    register() {
      this.$emit('submit', 'ID');
      this.close();
    },
  },
};
</script>

<style scoped lang='scss'>
#runnersContainer{
  display: flex;
  flex-direction: row;

  #content{
    border: 1px solid red;
  }

  button{
    background: #25bb75;
  }
}
</style>
