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
        <div>
          <p>Nome: {{runner.name}}</p>
          <p>Data de Nascimento: {{runner.birth}}</p>
        </div>
        <div>
          <p>Idade: {{18}}</p>
          <p>CPF: {{runner.cpf}}</p>
        </div>
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
}

</style>
