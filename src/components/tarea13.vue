<template>
    <div>
        <input type="text" name="" id="idNumero">
        <button v-on:click="buscar">Buscar</button>
        <br>
        <br>
        <label for="" id="idNombre">{{nombre}}</label>
        <br>
        <br>
        <img :src="imagen" alt="" v-if="imagen">
    </div>
</template>

<script>
export default {
    data(){
        return{
            nombre: '',
            imagen: null
        }
    },
    methods:{
        async obtenerRespuesta(num){
            const {name} = await fetch('https://pokeapi.co/api/v2/pokemon/'+num).then(r => r.json())
            console.log(name)
            this.nombre = name
            this.imagen = 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/'+num+'.svg';
        },
        buscar(){
            this.obtenerRespuesta(document.getElementById('idNumero').value)
        }

    },
    
}
</script>

<style scoped>
#idNombre{
    text-transform: uppercase;
    padding: 1em;
    color: white;
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
}

</style>