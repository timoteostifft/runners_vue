<template>
  <div class="modal-backdrop">
    <div class="modal">
      <div id='header'>
        <h3>Cadastro de Corredor</h3>
        <button @click="cancel">
          <img alt="Remove Icon" src="../assets/removeIcon.png" />
        </button>
      </div>

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
