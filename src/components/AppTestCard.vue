<template>
<div id="container">
  <div id="content">
    <!-- <img alt="App logo" src="../assets/runner.png">
    <div id="info">
      <p>Data: <span>22/04/2022</span></p>
      <p>Quilomêtros: <span>23km</span></p>
      <p>Participantes: <span>20</span></p>
    </div>
    <nav>
      <button>X</button>
      <button>X</button>
      <button>X</button>
    </nav> -->
  </div>
</div>
</template>

<script>
export default {
  name: 'AppTestCard',
};
</script>

<style scoped lang="scss">
  #container{
    width: 100%;
    max-width: 350px;
    height: 2rem;

    margin: 0 20px;

    & + &{
      margin-top: 30px;
    }

    @media (min-width: 848px) {
      & + &{
        margin-top: 30px;
      }

      &:first-child{
        margin-top: 30px;
      }
    }

    border: 1px solid red;

    #content{
    }
  }
</style>
