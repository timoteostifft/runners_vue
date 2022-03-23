<template>
<div id="container">
  <div id="content">
    <img id="mainImage" alt="App logo" src="../assets/runner.png">
    <div id="info">
      <p>Data: <span>20/04/2022</span></p>
      <p>Extensão: <span>24 KM</span></p>
      <p>Participantes: <span>42</span></p>
    </div>
    <nav>
      <button id="removeButton">
        <img alt="Remove Icon" src="../assets/removeIcon.png">
      </button>
      <button id="listButton">
        <img alt="List Icon" src="../assets/listIcon.png">
      </button>
      <button id="addButton">
        <img alt="Register Icon" src="../assets/addIcon.png">
      </button>
    </nav>
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
    height: 8.75rem;

    margin: 0 20px;

    & + &{
      margin-top: 55px;
    }

    &:last-child{
        margin-bottom: 55px;
      }

    @media (max-width: 600px) {
      margin: 0;
    }

    @media (min-width: 844px) {
      & + &{
        margin-top: 55px;
      }

      &:first-child{
        margin-top: 55px;
      }
    }

    #content{
      width: 100%;
      height: 100%;

      display: flex;
      flex-direction: row;

      background: #e7eaee;
      border: 3px solid #3a628d;
      border-radius: 1rem;
      box-shadow: rgba(0, 0, 0, 0.4) 0px 10px 20px 0px;

      #mainImage{
        height: 100%;
        width: 5rem;

        border-radius: 12px 0 0 12px;
        border-right: 3px solid #3a628d;
      }

      #info{
        margin-left: 12px;

        display: flex;
        flex-direction: column;

        p{
          color: #3a628d;
          font-weight: 500;
          font-size: 14px;
        }
      }

      nav{
        display: flex;
        flex-direction: column;

        margin: auto 4px auto auto;

        button{
          height: 35px;
          width: 35px;

          border-radius: 1rem;
          border: none;

          & + button{
            margin-top: 14px;
          }

          &:nth-child(1){
            background: #E52e4d;

            img{
              margin: 0 auto;
              height: 18px;
              width: auto;
            }
          }

          &:nth-child(2){
            background: #2e4c6d;

            img{
              margin: 0 auto;
              height: 16px;
              width: auto;
            }
          }

          &:nth-child(3){
            background: #24c077;

            img{
              margin: 0 auto;
              height: 18px;
              width: auto;
            }
          }
        }
      }
    }
  }
</style>
