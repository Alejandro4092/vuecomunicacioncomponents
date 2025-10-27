<template>
  <h1>{{nombredeporte}}</h1>
</template>

<script>
export default {
 name: "HijoDeporte",
 props:["nombredeporte"],
 mounted(){
    console.log("Deporte recibido: "+this.nombredeporte);
 }
}
</script>

<style>

</style>