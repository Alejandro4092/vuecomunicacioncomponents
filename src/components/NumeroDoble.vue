<template>
    <div>
        <h1>Numero Doble</h1>
        <h2 style="color:red">{{mensaje}}</h2>
    </div>
</template>

<script>
export default {
name:"NumeroDoble",
data(){
    return{
        mensaje:""
    }
},
mounted(){
    //Los parametros siempre son String ,no importa si son numericos
    console.log("Param:"+this.$route.params.numero)
    let numero=this.$route.params.numero;
    if(numero==""){
        this.mensaje="Sin parámetro en routing";
    }else{
        this.mensaje="Parametro recibido:"+numero;
    }
}
}
</script>

<style>

</style>