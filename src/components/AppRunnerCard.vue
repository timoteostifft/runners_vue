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
          <p>Idade: {{runner.age}}</p>
          <p>CPF: {{runner.cpf}}</p>
          <p>Tempo: {{runner.time}}</p>
        </div>
        <nav>
          <button @click='remove(test.id, runner)'>
            <img alt="Remove Icon" src="../assets/removeIcon.png" />
          </button>
          <button @oclick='edit()'>
            E
          </button>
        </nav>
      </div>
    </div>
  </div>
</template>

<script>
import api from '../plugins/api';

export default {
  name: 'AppRunnerForm',
  props: ['test'],
  methods: {
    close() {
      this.$emit('close');
    },
    async remove(id, runner) {
      await api
        .delete(`/tests/remove/${id}/${runner.id}`)
        .then((response) => {
          console.log(response.status);
        })
        .catch((error) => {
          console.log(error);
        });
      console.log(id, runner.name);
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

  div{
    display: flex;
    flex-direction: column;
  }

  nav{
    margin-left: auto;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    :nth-child(1){
      background: #e52e4d;
    }
    :nth-child(2){
      font-weight: 500;
      color: white;
      background: #3a628d;
    }
    button{
      border-radius: 16px;
      width: 30px;
      height: 30px;

      img{
        height: 16px;
        width: auto;
      }
    }
  }
}

</style>
