<template>
  <div class="modal-backdrop">
    <div class="modal">
      <div id='header'>
        <h3>Inserir resultado</h3>
        <button @click="close">
          <img alt="Remove Icon" src="../../../../assets/removeIcon.png" />
        </button>
      </div>

      <form action="">
        <label for="name">
          Início:
          <input name="start" type="time" v-model='form.start'>
        </label>
        <label for="name">
          Conclusão:
          <input name="start" type="time" v-model='form.finish'>
        </label>
      </form>

      <div id="footer">
        <button @click="close">
          SAIR
        </button>
        <button type="submit" @click='submit'>
          SALVAR
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AppRunnerForm',
  methods: {
    close() {
      this.$emit('close');
    },
    submit() {
      this.$emit('submit', this.form);
    },
  },
  data() {
    return {
      form: {
        start: '',
        finish: '',
      },
    };
  },
};
</script>

<style scoped lang='scss'>
.modal-backdrop{
  z-index: 9999;
}
</style>
