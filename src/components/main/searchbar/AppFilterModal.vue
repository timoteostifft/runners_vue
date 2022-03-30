<template>
  <div class="modal-backdrop">
    <div class="modal">
      <div id='header'>
        <h3>Filtro de Listagem</h3>
        <button @click="close">
          <img alt="Remove Icon" src="../../../assets/removeIcon.png" />
        </button>
      </div>

      <div id="main">
        <button @click="select('age')">
          Idade
        </button>
        <button @click="select('result')">
          Resultado
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AppFilterModal',
  methods: {
    select(value) {
      this.$emit('select', value);
      this.close();
    },
    close() {
      this.$emit('close');
    },
  },
};
</script>

<style scoped lang='scss'>
#main{
  margin-top: 2rem;
  max-width: 30rem;
  display: flex;
  flex-direction: row;
  justify-content: space-between;

  button{
    color: white;
    padding: 0.8rem;
    border-radius: 12px;
    width: 100%;
  }

  :nth-child(1){
    margin-right: 0.5rem;
    background: #46568f;
  }

  :nth-child(2){
    margin-left: 0.5rem;
    background: #25bb75;
  }
}
</style>
