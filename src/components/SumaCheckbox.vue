<template>
<div>
  <h1>Ejemplo Checkbox</h1>
  <form v-on:submit.prevent="agregarCheckbox()">
  <div v-for="cb in checkboxes" :key="cb.id">
      <input type="checkbox" v-model="cb.checked" :id="'cb-'+cb.id" @change="SumaTotal()"/>
      <label :for="'cb-'+cb.id">{{ cb.label }}</label>
    </div>
    <button >Agregar checkbox</button>
  </form>
   <h4>{{suma}}</h4>
  </div>
</template>

<script>
export default {
  name: "SumaCheckbox",
  data() {
    return {
      checkboxes: [],
      suma:0

    }
  },
  
  methods: {
    agregarCheckbox() {
      var numeroCheckbox=Math.floor(Math.random() * 100) + 1;
      const id = this.checkboxes.length + 1
      this.checkboxes.push({ id, label:numeroCheckbox})
    },
    SumaTotal(){
      this.suma=0;
      this.checkboxes.forEach(cb=>{
        if(cb.checked){
          this.suma+=cb.label;
        }
      })
      console.log("Suma total: "+this.suma)
    }
  }
}
</script>

<style>

</style>