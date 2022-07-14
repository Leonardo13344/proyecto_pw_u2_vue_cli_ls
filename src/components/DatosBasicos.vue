<template>

<h1>Datos Básicos</h1>
<label for="">Nombre {{tipo}}</label>
<br>
<input type="text" name="" id="idNombre">
<br>

<label for="">Apellido {{tipo}}</label>
<br>
<input type="text" name="" id="idApellido">
<br>

<label for="">Correo {{tipo}}</label>
<br>
<input type="text" name="" id="idCorreo">
<br>


</template>

<script>
export default{
    name: "Datos",
    props:{
        tipo: String
    },



data(){
    return {
        tipo: this.tipo
    }
}
}
</script>

<style>

</style>