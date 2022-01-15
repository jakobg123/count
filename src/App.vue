<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <Base />
  </div>
</template>

<script>
import Base from "./components/Base.vue"

export default {
  name: 'App',
  components: {
    Base
  }
}
</script>

<style lang="scss">
body{
    background-color: mediumaquamarine;
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
