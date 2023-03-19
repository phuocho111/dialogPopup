<template>
  <div id="app">
    <elicAi/>
  </div>
</template>

<script>
import elicAi from './components/elicAi.vue';
export default {
  components: {
    elicAi
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
