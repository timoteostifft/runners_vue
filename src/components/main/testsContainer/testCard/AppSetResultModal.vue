<template>
  <div class="modal-backdrop">
    <div class="modal">
      <div id='header'>
        <h3>Inserir resultado</h3>
        <button @click="close">
          <img alt="Remove Icon" src="../../../../assets/removeIcon.png" />
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
  },
};
</script>

<style scoped lang='scss'>
.modal-backdrop{
  z-index: 9999;
}
</style>
