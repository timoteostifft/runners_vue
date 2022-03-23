<template>
<div id="container">
  <div id="content">
    <img alt="App logo" src="../assets/runner.png">
    <div id="info">
      <p>Data: 22/04/2022</p>
      <p>Quilomêtros: 23Km</p>
      <p>Participantes: 20</p>
    </div>
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
    max-width: 530px;

    padding: 0 1rem;
    margin: 0 auto 2rem;

    #content{
      height: 6rem;

      display: flex;
      justify-content: row;

      border: 3px solid #3a628d;
      background: #e7eaee;
      border-radius: 1rem;
      box-shadow: rgba(0, 0, 0, 0.4) 0px 10px 20px 0px;

      img{
        border-right: 3px solid #3a628d;

        border-radius: 14.5px 0 0 14.5px;
        margin-left: -1px;

        height: 100%;
        width: 4.5rem;
      }

      #info{
        display: flex;
        flex-direction: column;

        p{
          margin: auto 6px;
          font-size: 14px;
        }
      }
    }
  }
</style>
