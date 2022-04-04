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
        <div class='buttons'>
          <button @click='()=>{$emit("remove",runner.id)}'>
            <img src="../../../../assets/binIcon.png" alt="">
          </button>
          <button @click="()=>{handleUseModal()}">
            <img src="../../../../assets/editIcon.png" alt="">
          </button>
        </div>
      </div>
      <AppSetResultModal v-show='isModalVisible'/>
      <h4 v-show='test.youngerThan25'>Até 25 anos: </h4>
      <div class='younger'>
        <div class='content' v-for="runner in test.youngerThan25" :key="runner.id">
          <div class='info'>
            <p>Nome: {{runner.name}}</p>
            <p>CPF: {{runner.cpf}}</p>
            <p>Nascimento: {{runner.birth}}</p>
            <p>Idade: {{runner.age}}</p>
          </div>
          <div class='ageButtons'>
            <button @click='()=>{$emit("remove",runner.id)}'>
              <img src="../../../../assets/binIcon.png" alt="">
            </button>
          </div>
        </div>
      </div>
      <h4 v-show='test.youngerThan35'>Até 35 anos: </h4>
      <div class='younger'>
        <div class='content' v-for="runner in test.youngerThan35" :key="runner.id">
          <div class='info'>
            <p>Nome: {{runner.name}}</p>
            <p>CPF: {{runner.cpf}}</p>
            <p>Nascimento: {{runner.birth}}</p>
            <p>Idade: {{runner.age}}</p>
          </div>
          <div class='ageButtons'>
            <button @click='()=>{$emit("remove",runner.id)}'>
              <img src="../../../../assets/binIcon.png" alt="">
            </button>
          </div>
        </div>
      </div>
      <h4 v-show='test.youngerThan45'>Até 45 anos: </h4>
      <div class='younger'>
        <div class='content' v-for="runner in test.youngerThan45" :key="runner.id">
          <div class='info'>
            <p>Nome: {{runner.name}}</p>
            <p>CPF: {{runner.cpf}}</p>
            <p>Nascimento: {{runner.birth}}</p>
            <p>Idade: {{runner.age}}</p>
          </div>
          <div class='ageButtons'>
            <button @click='()=>{$emit("remove",runner.id)}'>
              <img src="../../../../assets/binIcon.png" alt="">
            </button>
          </div>
        </div>
      </div>
      <h4 v-show='test.youngerThan55'>Até 55 anos: </h4>
      <div class='younger'>
        <div class='content' v-for="runner in test.youngerThan55" :key="runner.id">
          <div class='info'>
            <p>Nome: {{runner.name}}</p>
            <p>CPF: {{runner.cpf}}</p>
            <p>Nascimento: {{runner.birth}}</p>
            <p>Idade: {{runner.age}}</p>
          </div>
          <div class='ageButtons'>
            <button @click='()=>{$emit("remove",runner.id)}'>
              <img src="../../../../assets/binIcon.png" alt="">
            </button>
          </div>
        </div>
      </div>
      <h4 v-show='test.olderThan55'>Após 55 anos: </h4>
      <div class='younger'>
        <div class='content' v-for="runner in test.olderThan55" :key="runner.id">
          <div class='info'>
            <p>Nome: {{runner.name}}</p>
            <p>CPF: {{runner.cpf}}</p>
            <p>Nascimento: {{runner.birth}}</p>
            <p>Idade: {{runner.age}}</p>
          </div>
          <div class='ageButtons'>
            <button @click='()=>{$emit("remove",runner.id)}'>
              <img src="../../../../assets/binIcon.png" alt="">
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import AppSetResultModal from './AppSetResultModal.vue';

export default {
  name: 'AppRunnerForm',
  props: ['test'],
  components: {
    AppSetResultModal,
  },
  data() {
    return {
      isModalVisible: false,
    };
  },
  methods: {
    close() {
      this.$emit('close');
    },
    handleUseModal() {
      this.isModalVisible = !this.isModalVisible;
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

  .buttons{
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
.younger{
  .content{
    display: flex;
    flex-direction: row;
    align-items: center;

    margin-top: 10px;
    border-bottom: 1px solid #3a628d;

    .info{
      display: flex;
      flex-direction: column;
    }
    .ageButtons{
      display: flex;
      flex-direction: column;

      margin-left: auto;

      button{
        margin: auto 2.5px 10px auto;
        border-radius: 16px;
        padding: 8px 8.5px;

        img {
          height: 14px;
          width: 12px;
        }
      }

      :nth-child(1){
        background: #e52e4d;
      }

      :nth-child(2){
        background: #46568f;
      }
    }
  }
}

h4{
  margin-top: 1rem;
}

</style>
