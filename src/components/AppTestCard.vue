<template>
<div id="container">
  <div id="content">
    teste
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
    max-width: 790px;

    padding: 0 1rem;
    margin: 0 auto 2rem;

    #content{
      height: 6rem;

      border: 3px solid #3a628d;
      background: #e7eaee;
      border-radius: 1rem;
      box-shadow: rgba(0, 0, 0, 0.4) 0px 10px 20px 0px;
    }
  }
</style>
