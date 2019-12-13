<template>
  <div id="app">
    <img src="./assets/logo.png">
    <div class="subtitle">Remove unused css class or inline style.</div>
    <Remover/>
  </div>
</template>

<script>
import Remover from './components/Remover.vue'

export default {
  name: 'app',
  components: {
    Remover
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
.subtitle{
  margin-top: 1em;
  margin-bottom: 1em;
  font-size: 1.3em;
}
</style>
