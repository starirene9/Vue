<template>
  <!-- template 안에 HTML -->
  <img alt="Vue logo" src="./assets/logo.png">
  Hello World!
  <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>
//JS 작성
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
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
