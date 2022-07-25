<template>
  
  <!--<HelloWorld msg="Bienvenido to Your Vue.js App"/>-->
  <tarea14 />
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Contador from './components/Contador.vue'
import tarea14 from './components/tarea14.vue'

export default {
  name: 'App',
  components: {
    tarea14
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

body{
  background: black;
}
</style>
