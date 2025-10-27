<template>
  <HijoDeporte></HijoDeporte>
  <div>
    <h1 style="color:blue">Padre Deportes</h1>
    <ul>
      <li v-for="sport in deportes" :key="sport">
        <HijoDeportes :nombredeporte="sport"/>
      </li>
    </ul>
  </div>
</template>

<script>
import HijoDeporte from './HijoDeporte.vue'

export default {
  name:"PadreDeportes",
  components:{
    HijoDeporte
  },
  data(){
  return{
        deportes:["Curling","Esgrima","Hockey sobre hielo"]
    }
  }

}
</script>


<style>

</style>