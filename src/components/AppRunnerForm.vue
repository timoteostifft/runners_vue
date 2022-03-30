<template>
  <div class="modal-backdrop">
    <div class="modal">
      <div id='header'>
        <h3>Cadastro de Corredor</h3>
        <button @click="cancel">
          <img alt="Remove Icon" src="../assets/removeIcon.png" />
        </button>
      </div>
      <form action="">
        <label for="name">
            Nome:
          <input type="text" name='name' id='name' required v-model='form.name'>
        </label>

        <label for="birth">
          Data de Nascimento:
          <input type="date" name='name' id='name' required v-model='form.birth'>
        </label>

        <label for="cpf">
          Data de Nascimento:
          <input type="number" name='cpf' id='cpf' required v-model='form.cpf'>
        </label>
      </form>

      <div id="footer">
        <button @click="close">
          CANCELAR
        </button>
        <button type="submit" @click='cancel'>
          CADASTRAR
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AppRunnerForm',
  data() {
    return {
      form: {
        name: String,
        birth: String,
        cpf: String,
      },
    };
  },
  methods: {
    close() {
      this.$emit('cancel');
    },
    submit() {
      this.$emit('submit', this.form);
    },
  },
};
</script>

<style scoped lang='scss'>
</style>
