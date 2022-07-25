<template>
    <div>
        <h1>Consumo API pública IP's</h1>
        <br>
        <input type="text" placeholder="Ingrese una IP" id="idIP">
        <button v-on:click="buscar">Buscar</button>
        <br>
        <br>
        <br>
        <table class="tg">
            <thead>
                <tr>
                    <th class="tg-c3ow">Type</th>
                    <th class="tg-c3ow">Continent</th>
                    <th class="tg-c3ow">Country</th>
                    <th class="tg-c3ow">Region</th>
                    <th class="tg-c3ow">City</th>
                    <th class="tg-0lax">Organization</th>
                    <th class="tg-0lax">ISP</th>
                    <th class="tg-0lax">Image</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td class="tg-svo0">{{type}}</td>
                    <td class="tg-svo0">{{continent}}</td>
                    <td class="tg-svo0">{{country}}</td>
                    <td class="tg-svo0">{{region}}</td>
                    <td class="tg-svo0">{{city}}</td>
                    <td class="tg-hmp3">{{org}}</td>
                    <td class="tg-hmp3">{{isp}}</td>
                    <td class="tg-hmp3"><img :src="img" alt="" v-if="img"></td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
export default {
    data(){
        return{
            type: '',
            continent: '',
            country: '',
            region: '',
            city: '',
            org: '',
            isp: '',
            img: ''
        }
    },
    methods: {
        async respuesta(value){
            const {type, continent, country, region, city, connection:{org}, connection:{isp}, flag:{img}} = await fetch('https://ipwho.is/'+value).then(r => r.json()) 
            this.type = type
            this.continent = continent
            this.country = country
            this.region = region
            this.city = city
            this.org = org
            this.isp = isp
            this.img = img;
        },
        buscar(){
            this.respuesta(document.getElementById('idIP').value)
        }
    }
}
</script>

<style scoped>
div {
    color: white;
}

table{
    margin: auto;
}

.tg {
    border-collapse: collapse;
    border-color: #3cbbb1;
    border-spacing: 0;
}

.tg td {
    background-color: #e8edff;
    border-bottom-width: 1px;
    border-color: #3cbbb1;
    border-style: solid;
    border-top-width: 1px;
    border-width: 0px;
    color: #669;
    font-family: Arial, sans-serif;
    font-size: 14px;
    overflow: hidden;
    padding: 10px 5px;
    word-break: normal;
}

.tg th {
    background-color: #b9c9fe;
    border-bottom-width: 1px;
    border-color: #3cbbb1;
    border-style: solid;
    border-top-width: 1px;
    border-width: 0px;
    color: #039;
    font-family: Arial, sans-serif;
    font-size: 14px;
    font-weight: normal;
    overflow: hidden;
    padding: 10px 5px;
    word-break: normal;
}

.tg .tg-hmp3 {
    background-color: #D2E4FC;
    text-align: center;
    vertical-align: middle;
}

.tg .tg-c3ow {
    border-color: inherit;
    text-align: center;
    vertical-align: top;
}

.tg .tg-0lax {
    text-align: center;
    vertical-align: top;
}

.tg .tg-svo0 {
    background-color: #D2E4FC;
    border-color: inherit;
    text-align: center;
    vertical-align: middle;
    
}

img{
    width: 200px;
    height: 200px;
}
</style>