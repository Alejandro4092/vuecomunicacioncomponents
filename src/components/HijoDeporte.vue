<template>
    <div>
        <h4 style="color:red">{{ nombredeporte }}</h4>
        <button @click="seleccionarFavorito">Seleccionar Favorito</button>
    </div>
</template>

<script>
    export default {
        name: "HijoDeporte",
        props: ["nombredeporte"]
        , mounted() {
            console.log(this.nombredeporte)
        },methods:{
          seleccionarFavorito(){
            console.log("Soy el hijo "+this.nombredeporte);
            //para enviar informacion se realiza a partir de la llamada 
            //con cada parametro separado con comas, dentro del metodo emit
            this.$emit("seleccionarFavoritoParent",this.nombredeporte)
          }
        }
    }
</script>