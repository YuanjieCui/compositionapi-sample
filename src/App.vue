<template>
  <div id="app">
    <Position/>
  </div>
</template>

<script>
import Position from './components/Position/Position.vue'

export default {
  name: 'App',
  components: {
    Position,
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
