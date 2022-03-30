<template>
  <div class="modal-backdrop">
    <div class="modal">
      <div id='header'>
        <h3>Listagem de Corredores</h3>
        <button @click="()=>{this.$emit('close')}">
          <img alt="Remove Icon" src="../../assets/removeIcon.png" />
        </button>
      </div>

      <div id="formContainer">
        <form action="">
        <label for="name">
          Nome:
          <input
            type="text"
            name='name'
            id='name' required
            placeholder="Digite aqui"
            v-model='form.name'
          >
        </label>

        <label for="cpf">
          CPF:
          <input
            type="text"
            name='cpf'
            id='cpf' required
            placeholder="XXX.XXX.XXX-XX"
          >
        </label>

        <label for="birth">
          Nascimento:
          <input
            type="text"
            name='birth'
            id='birth' required
            placeholder="YY/MM/DD"
          >
        </label>
        </form>
        <button @click="register">
          <img alt="Remove Runner Icon" src="../../assets/addIcon.png" />
        </button>
      </div>

      <div id="main">
        <form action=""></form>
        <div id='runnerContainer' v-for="runner in runners" :key="runner.id">
          <div id="data">
            <p>Nome: {{runner.name}}</p>
            <p>CPF: {{runner.cpf}}</p>
            <p>Data de Nascimento: {{runner.birth}}</p>
          </div>
          <button @click="remove(runner)">
            <img alt="Remove Runner Icon" src="../../assets/binIcon.png" />
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AppRunnersModal',
  props: ['runners'],
  methods: {
    remove(runner) {
      this.$emit('remove', runner);
    },
    register() {
      this.$emit('register', this.form);
    },
  },
  data() {
    return {
      form: {
        name: '',
        cpf: '',
        birth: '',
      },
    };
  },
};
</script>

<style scoped lang='scss'>

#formContainer{
  display: flex;
  flex-direction: row;

  form{
    font-size: 15px;

    label{
      height: 16px;
      input{
        &::placeholder {
          color: #3a628d;
          opacity: 0.9;
        }
      }
    }

  }

  button{
    margin: auto 1.5px auto auto;
    border-radius: 16px;
    background: #25bb75;
    padding: 8px 8.5px;

    img {
      height: 14px;
      width: 12px;
    }
  }
}

#runnerContainer{
  display: flex;
  flex-direction: row;
  align-items: center;

  & + #runnerContainer{
      margin-top: 1rem;
    }

  #data{
    display: flex;
    flex-direction: column;

    font-size: 14.5px;
    border-bottom: 1px solid #3a628d;
  }
  button{
    margin: auto 1.5px auto auto;
    border-radius: 16px;
    background: #e52e4d;
    padding: 8px 8.5px;

    img {
      height: 14px;
      width: 12px;
    }
  }
}
</style>
