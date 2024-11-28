<template>
  <div id="app">
    <ChessGrandmasters />
  </div>
</template>

<script>
import ChessGrandmasters from './components/ChessGrandmasters.vue';

export default {
  name: 'App',
  components: {
    ChessGrandmasters
  }
};
</script>

<style>
#app {
  text-align: center;
  margin-top: 20px;
}
</style>
