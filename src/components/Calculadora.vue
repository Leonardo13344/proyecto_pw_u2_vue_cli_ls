<template>
    <h2>Calculadora</h2>
    <label for="idNum1">#1</label>
    <input type="text" name="" id="idNum1">
    <input type="text" name="" id="idNum2">
    <label for="idNum2">#2</label>

    <div class="n1">
        <button v-on:click="calcular('S')">
            +
        </button>
        <button v-on:click="calcular('R')">
            -
        </button>
        <button v-on:click="calcular('D')">
            /
        </button>
        <button v-on:click="calcular('M')">
            X
        </button>
    </div>

    <div class="n1">
        <label for="" id="idR">{{ r }}</label>
    </div>

</template>

<script>

export default {
    name: "calcu",
    data() {
        return {
            n1: 1,
            n2: 1,
            r: 1
        }
    },
    methods: {
        calcular(tipo) {
            document.getElementById("idR").style.visibility = "visible";
            this.n1 = document.getElementById("idNum1").value;
            this.n2 = document.getElementById("idNum2").value;
            if (tipo === "S") {
                this.r = parseInt(this.n1) + parseInt(this.n2);
                return this.r;
            } else if (tipo === "R") {
                this.r = parseInt(this.n1) - parseInt(this.n2);
                return this.r;
            } else if (tipo === "D") {
                this.r = parseInt(this.n1) / parseInt(this.n2);
                return this.r;
            } else if (tipo === "M") {
                this.r = parseInt(this.n1) * parseInt(this.n2);
                return this.r;
            }
        }
    }
}
</script>

<style scoped>
button {
    color: black;
}

div {
    margin-top: .5em;
    margin-bottom: .5em;
}

#idR {
    visibility: hidden;
}
</style>