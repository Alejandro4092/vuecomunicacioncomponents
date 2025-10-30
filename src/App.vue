<template>
  
  <MenuComponent/>
  <router-view></router-view>
 
</template>

<script>

//import PadreNumeros from './components/PadreNumeros.vue'
//import PadreDeportes from './components/PadreDeportes.vue';
//import ComicsComponent from './components/ComicsComponent.vue'
// import SeleccionMultiple from './components/SeleccionMultiple.vue'
// import SumaCheckbox from './components/SumaCheckbox.vue'
import MenuComponent from './components/MenuComponent.vue'



export default {
  name: 'App',
  components: {
    MenuComponent
    // SumaCheckbox
    // SeleccionMultiple,
   // ComicsComponent,
   // PadreDeportes,
   // PadreNumeros,
  
    

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
}
</style>