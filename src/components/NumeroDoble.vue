<template>
    <div>
        <h1>Numero Doble</h1>
        <h2 style="color:red">{{mensaje}}</h2>
        <h2 style="color:blue">{{doble}}</h2>
        <button @click="redirectToHome()">Volver al home</button>
    </div>
</template>

<script>
export default {
name:"NumeroDoble",
data(){
    return{
        mensaje:"",
        doble:0
    }
},
methods:{
    redirectToHome(){
        this.$router.push("/");
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
        this.doble=parseInt(numero)*2;
    }
},
watch:{
    '$route.params.numero' (nextVal,oldVal){
        if(nextVal!=oldVal){
            this.mensaje="Esto ha cambiado: "
       + this.$route.params.numero;
       this.doble=parseInt(this.$route.params.numero)*2;
        console.log("Next:"+nextVal);
        console.log("Old:"+oldVal);
        }
        
    }
}
}
</script>

<style>

</style>