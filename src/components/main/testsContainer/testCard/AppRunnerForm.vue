<template>
  <div class="modal-backdrop">
    <div class="modal">
      <div id='header'>
        <h3>Cadastro de Corredor</h3>
        <button @click="close">
          <img alt="Remove Icon" src="../../../../assets/removeIcon.png" />
        </button>
      </div>

      <div id="body">
        <div id='runnersContainer' v-for="runner in runners" :key="runner.id">
          <div id='content'>
            <p>Nome: {{runner.name}}</p>
            <p>CPF: {{runner.cpf}}</p>
            <p>Nascimento: {{runner.birth}}</p>
          </div>
          <button @click="register(runner.id)">
            <img alt="Add Icon" src="../../../../assets/addIcon.png">
          </button>
        </div>
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
    register(id) {
      this.$emit('submit', id);
      this.close();
    },
  },
};
</script>

<style scoped lang='scss'>
#runnersContainer{
  display: flex;
  flex-direction: row;
  margin-top: 2rem;
  border-bottom: 1px solid #3a628d;

  & + #runnersContainer{
    margin-top: 1rem;
  }
  button{
    margin: auto 2.5px auto auto;
    border-radius: 16px;
    background: #25bb75;
    padding: 8px 8.5px;

    img {
      height: 14px;
      width: 12px;
    }
  }
}
</style>
