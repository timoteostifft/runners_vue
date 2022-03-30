<template>
  <div class="modal-backdrop">
    <div class="modal">
      <div id='header'>
        <h3>Cadastro de Corridas</h3>
        <button @click="close">
          <img alt="Remove Icon" src="../assets/removeIcon.png" />
        </button>
      </div>
      <form action="">
        <label for="date">
          Data:
          <input type="date" name='date' id='date' required v-model='form.date'>
        </label>

        <label for="type">
          Distância:
          <select name="type" id='type' v-model='form.type'>
            <option value="3">3</option>
            <option value="5">5</option>
            <option value="10">10</option>
            <option value="21">21</option>
            <option value="21">42</option>
          </select>
          <p>quilômetros</p>
        </label>
      </form>

      <div id="footer">
        <button @click="close">
          SAIR
        </button>
        <button type="submit" @click='submit'>
          CADASTRAR
        </button>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'AppTestForm',
  data() {
    return {
      form: {
        type: String,
        date: String,
      },
    };
  },
  methods: {
    close() {
      this.$emit('close');
    },
    submit() {
      this.$emit('submit', this.form);
    },
  },
};
</script>

<style lang='scss'>

    #header{
      display: flex;
      align-items: center;
      flex-direction: row;

      h3{
        font-weight: 600;
        font-size: 18px;
      }

      button{
        height: 35px;
        width: 35px;

        margin-left: auto;

        border: none;
        border-radius: 1rem;

        background: #e52e4d;
        img{
          height: 18px;
          width: auto;
        }
      }
    }

    form{

      margin-top: 1.2rem;
      display: flex;
      flex-direction: column;

      label{
        align-items: center;
        font-weight: 500;

        display: flex;

        select{
          margin-left: 6px;
          line-height: 18px;
          border-bottom: 1px solid #3a628d;
          color: #3a628d;

          cursor: pointer;

          &::placeholder {
            opacity: 0.85;
          }

          &:focus {
            outline: none;
          }
        }

        p{
          margin-left: 6px;
        }

        input{
          color: #3a628d;
          width: 100%;

          margin-left: 10px;

          cursor: text;

          &:focus {
            outline: none;
          }
        }

        & + label {
          margin-top: 1rem;
        }
      }
    }

    #footer{
      margin-top: 2rem;

      display: flex;
      flex-direction: row;

      color: white;

      button{
        border-radius: 0.2rem;
        height: 3rem;
        width: 100%;
      }

      :nth-child(1){
        margin-right: 8px;
        background: #e52e4d;
      }

      :nth-child(2){
        margin-left: 8px;
        background: #25bb75;
      }
    }

</style>
