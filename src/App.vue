<template>
  <div id="app" class="app">
    <Calculator />
  </div>
</template>

<script>
import Calculator from './components/Calculator'
export default {
  name: 'App',
  components: {
    Calculator
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
