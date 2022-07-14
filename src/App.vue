<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <!--<HelloWorld msg="Bienvenido to Your Vue.js App"/>-->
  <!--<Contador2 titulo="Titulo1"  v-bind:inicio = "valorInicio" />-->
  <!--<Contador2 titulo="Titulo3" v-bind:inicio="-1" />-->
  <!--<Calculadora />-->
  <DatosBasicos v-bind:tipo="tipo"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Contador from './components/Contador.vue'
import Contador2 from './components/Contador2.vue'
import Calculadora from './components/Calculadora.vue'
import DatosBasicos from './components/DatosBasicos.vue'

export default {
  name: 'App',
  data(){
    return{
      valorInicio: 27,
      tipo: "Estudiante"
    }
  },
  components: {
    Contador,
    Calculadora,
    Contador2,
    DatosBasicos
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
