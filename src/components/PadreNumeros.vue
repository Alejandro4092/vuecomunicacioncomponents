<template>
  <h1>Numeros Padre</h1>
  <h2 style="color:red">La suma es {{ sumaTotal }}</h2>
  <button @click="GenerarNumeroAleatorio">Nuevo Número</button>

  <ul>
    <li v-for="(numbers, idx) in numeros" :key="numbers + '-' + idx">
      <HijoNumero :numero="numbers" v-on:sumar="sumarNumero"/>
    </li>
  </ul>
</template>


<script>
import HijoNumero from './HijoNumero.vue'

export default {
name:"PadreNumeros",
components:{
  HijoNumero
},
data(){
  return{
    numeros:[10,20,30,40],
    sumaTotal:0
  }
},methods:{
  GenerarNumeroAleatorio(){
    var numeroAleatorio=Math.floor(Math.random()*100)+1;
    this.numeros.push(numeroAleatorio)
},
sumarNumero(numero){
  console.log("Soy el padre y voy a sumar "+numero)

  this.sumaTotal += numero
}
}
}
</script>

<style>

</style>