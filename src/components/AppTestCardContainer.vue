<template>
<div id="testsContainer">
  <AppTestCard/>
  <AppTestCard/>
  <AppTestCard/>
  <AppTestCard/>
  <AppTestCard/>
  <AppTestCard/>
</div>
</template>

<script>
import AppTestCard from './AppTestCard.vue';

export default {
  name: 'App',
  components: {
    AppTestCard,
  },
};
</script>

<style scoped lang="scss">
#testsContainer{
  max-width: 840px;

  margin: 0 auto;
  padding: 0 2rem;

  display: flex;
  flex-wrap: wrap;
  justify-content: center;

  @media (min-width: 768px) {
    justify-content: space-around;
    }
}
</style>
