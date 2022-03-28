<template>
  <div class='modal-backdrop'>
    <div class='modal'>
       <div id='header'>
        <h3>Listagem de Corredores</h3>
        <button @click="close">
          <img alt="Remove Icon" src="../assets/removeIcon.png" />
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

  .modal-backdrop {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: rgba(0, 0, 0, 0.25);
    display: flex;
    justify-content: center;
    align-items: center;

    .modal {
      width: 30rem;
      padding: 1.5rem;

      background: #FFFFFF;
      box-shadow: rgba(0, 0, 0, 0.6) 0px 10px 20px 0px;

      color: #3a628d;
    }
  }

</style>
