<template>
  <div id="container">
    <div id="content">
      <h1>Listagem de <br><span>Corridas</span></h1>
    </div>
    <button>
      <img alt="Register Icon" src="../assets/addIcon.png">
    </button>
  </div>
</template>

<script>
export default {
  name: 'AppListTitle',
};
</script>

<style scoped lang="scss">
  #container{
    display: flex;
    max-width: 820px;
    margin: 0 auto;

    align-items: center;

    #content{
      padding: 0 2rem;

      margin-top: -20px;
      margin-bottom: -40px;

      h1{
        margin-top: -4px;
        color: #e7eaee;

        span{
          color: #4081c7;
        }

        @media (min-width: 640px) {
          br{
            display: none;
          }
        }
      }
    }

    button{
      margin-left: auto;
      margin-right: 20px;

      height: 35px;
      width: 35px;

      border: none;
      border-radius: 1rem;
      background: #25bb75;

      img{
        margin: 0 auto;
        height: 18px;
        width: auto;
      }
    }
  }
</style>
