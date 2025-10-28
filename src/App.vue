<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <CheckboxSuma/>
</template>

<script>
import CheckboxSuma from './components/CheckboxSuma.vue'


export default {
  name: 'App',
  components: {
    CheckboxSuma
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
