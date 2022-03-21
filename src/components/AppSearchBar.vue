<template>
<div id="container">
  <div id="content">
    <div id='searchArea'>
      <img alt="App logo" src="../assets/searchIcon.png">
      Pesquise aqui
    </div>
    <button id="filter">
      <img alt="App logo" src="../assets/filterIcon.png">
    </button>
  </div>
</div>
</template>

<script>
export default {
  name: 'AppSearchbar',
};
</script>

<style scoped lang="scss">

#container{
  display: flex;
  align-items: center;

  max-width: 820px;
  width: 100%;

  margin: 4rem auto 0;

  #content{
    display: flex;
    align-items: center;
    width: 100%;
    height: 3rem;

    padding: 0 1rem;

    #searchArea{
      display: flex;
      align-items: center;

      width: 100%;
      margin-right: 0.5rem;

      border: 3px solid #3a628d;
      background: #e7eaee;
      border-radius: 12rem 3rem 3rem 12rem;
      box-shadow: rgba(0, 0, 0, 0.4) 0px 10px 20px 0px;

      img{
        margin-left: -2.2px;
        height: 2.5rem;
        width: auto;

        margin-right: 0.5rem;
      }
    }

    #filter{
      height: 3rem;
      width: 3rem;

      display: flex;
      justify-content: center;
      align-items: center;

      border-radius: 10px;
      box-shadow: rgba(0, 0, 0, 0.4) 0px 10px 20px 0px;
      border: 3px solid #3a628d;

      cursor: pointer;

      img{
        height: 50%;
        width: auto;
      }
    }
  }
}
</style>
