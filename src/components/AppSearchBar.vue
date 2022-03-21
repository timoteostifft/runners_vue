<template>
<div id="container">
  <div id="content">
    <div id='searchArea'>
      <img alt="App logo" src="../assets/searchIcon.png">
    </div>
    <button id="filter"/>
  </div>
</div>
</template>

<script>
export default {
  name: 'AppSearchbar',
  props: {
    margin: String,
  },
};
</script>

<style scoped lang="scss">

#container{
  display: flex;
  align-items: center;

  max-width: 820px;
  width: 100%;

  margin: 4rem auto;

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
        height: 3rem;
        width: auto;
      }
    }

    #filter{
      //
    }
  }
}
</style>
