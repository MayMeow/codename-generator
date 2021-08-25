<template>
  <div id="app">
    <CodenameGenerator></CodenameGenerator>
  </div>
</template>

<script>
import CodenameGenerator from './components/Generator.vue'

export default {
  name: 'App',
  components: {
    CodenameGenerator
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
