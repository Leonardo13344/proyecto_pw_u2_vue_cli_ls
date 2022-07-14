<template>
    <!-- Html-->
    <h2>{{titulo || 'Titulo Vacio'}}</h2>
    <p>{{ numero }} <sup>2</sup> = {{ obtenerCuadradoComputado }}</p>
    <p>{{ numero }} <sup>2</sup> = {{ obtenerCuadradoComputado }}</p>
    <p>{{ numero }} <sup>2</sup> = {{ obtenerCuadradoComputado }}</p>
    <p>{{ numero }} <sup>2</sup> = {{ obtenerCuadradoComputado }}</p>
    <p>{{ numero }} <sup>2</sup> = {{ obtenerCuadradoComputado }}</p>

    <div>
        <button v-on:click="incrementar">
            +1
        </button>

        <button v-on:click="decrementar">
            -1
        </button>
    </div>

</template>

<script>

export default {
    name: "Contador123",
    props:{
        titulo: String,
        inicio: {
            type: Number,
            required: false,
            default: 100,
            validator(value){
                //Que retorne True o False
                return value > 0 
            }
        }

    },

    data() {
        return {
            numero: this.inicio,
        }
    },
    methods: {
        obtenerCuadrado() {
            console.log("Entrando a la potencia")
            return this.numero * this.numero
        },
        incrementar(){
            return this.numero = this.numero + 1
        },
        decrementar(){
            return this.numero--
        }
    },
    computed:{
        obtenerCuadradoComputado(){
            console.log("Entrando a la computado")
            return this.numero * this.numero
        },
        muestraTitulo(){
            return this.titulo || "Titulo vacio 2"
        }
    }
}
</script>
<!-- Estilos de mi componentes -->
<style>
button{
    background-color: #64BB87;
    border-radius: 5px;
    color: white;
    margin: 0 5px;
    cursor: pointer;    
}

button:hover{
    background-color: #5AA67B;
    transition: 0.1s ease-in-out;
}
</style>