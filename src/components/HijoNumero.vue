<template>
  <h1 style="color:blue">Número hijo: {{numero}}</h1>
  <button @click="sumarNumero" >Sumar {{numero}}</button>
</template>

<script>
export default {
    name:"HijoNumero",
    props:["numero"],
    mounted(){
        console.log(this.numero)
    },methods:{
        sumarNumero(){
            console.log("Sumando numero")
            this.$emit("sumarNumero", this.numero)
            

        }
    }

}
</script>

<style>

</style>