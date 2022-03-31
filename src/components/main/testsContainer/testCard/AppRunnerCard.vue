<template>
  <div class='modal-backdrop'>
    <div class='modal'>
       <div id='header'>
        <h3>Listagem de Corredores</h3>
        <button @click="close">
          <img alt="Remove Icon" src="../../../../assets/removeIcon.png" />
        </button>
      </div>
      <div id='container' v-for='runner in test.runners' :key='runner.id'>
        <div id='content'>
          <p>Nome: {{runner.name}}</p>
          <p>CPF: {{runner.cpf}}</p>
          <p>Nascimento: {{runner.birth}}</p>
          <p>Resultado: {{runner.time}}</p>
        </div>
        <div id='buttons'>
          <button @click='()=>{$emit("remove",runner.id)}'>
            <img src="../../../../assets/binIcon.png" alt="">
          </button>
          <button>
            <img src="../../../../assets/editIcon.png" alt="">
          </button>
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
  flex-direction: row;

  margin-top: 2rem;
  border-bottom: 1px solid #3a628d;

  & + #container{
    margin-top: 1rem;
  }

  #buttons{
    margin-left: auto;
    :nth-child(1){
      background: #e52e4d;
    }

    :nth-child(2){
      background: #46568f;
    }
  }

  button{
    margin: auto 2.5px 10px auto;
    border-radius: 16px;
    padding: 8px 8.5px;

    img {
      height: 14px;
      width: 12px;
    }
  }
}

</style>
