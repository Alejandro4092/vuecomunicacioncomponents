<template>
  <div>
    <h1>Tabla multiplicar</h1>
    <h2 style="color:red">{{mensaje}}</h2>
    <h2 style="color:blue">{{ numero }}</h2>
    <div class="tabla-wrap">
      <table class="tabla-multiplicar">
        <thead>
          <tr>
            <th>Multiplicando</th>
            <th>Operador</th>
            <th>Resultado</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="n in 10" :key="n">
            <td>{{ numero }}</td>
            <td>{{ n }}</td>
            <td>{{ numero * n }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: "TablaMultiplicar",
  data() {
    return {
      mensaje: "",
      numero: 0
    };
  },
  methods: {
    
  },
  mounted() {
    // Los parametros pueden ser undefined o cadena vacía
    console.log("Param:" + this.$route.params.numero);
    let numero = this.$route.params.numero;
    if (numero == "") {
      this.mensaje = "Sin Parametro en routing";
    } else {
      
      this.numero = numero;
    }
  },
  watch: {
    "$route.params.numero"(nextVal, oldVal) {
      if (nextVal != oldVal) {
      
        console.log("Next:" + nextVal);
        console.log("Old:" + oldVal);
        this.numero = this.$route.params.numero;
      }
    },
  },
};
</script>

<style scoped>
.tabla-wrap{
  display:flex;
  justify-content:center;
  margin-top:16px;
}
.tabla-multiplicar{
  border-collapse:collapse;
  width:100%;
  max-width:520px;
  background:#fff;
  box-shadow:0 6px 18px rgba(0,0,0,0.08);
  border-radius:8px;
  overflow:hidden;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
}
.tabla-multiplicar thead th{
  background: linear-gradient(90deg,#4f46e5,#06b6d4);
  color:white;
  padding:12px 16px;
  text-align:left;
  font-weight:600;
  font-size:14px;
}
.tabla-multiplicar tbody td{
  padding:12px 16px;
  border-top:1px solid rgba(0,0,0,0.06);
  font-size:15px;
  color:#0f172a;
}
.tabla-multiplicar tbody tr:nth-child(odd){
  background: #fbfdff;
}
.tabla-multiplicar tbody tr:hover{
  background: #eef2ff;
  transform: translateY(-1px);
}
h1{
  font-size:22px;
  margin-bottom:6px;
  color:#0f172a;
}
h2[style*="color:red"]{
  color:#dc2626 !important;
  margin:0 0 6px 0;
}
h2[style*="color:blue"]{
  color:#0b69ff !important;
  margin:0;
}
@media (max-width:600px){
  .tabla-multiplicar thead th{font-size:13px;padding:10px}
  .tabla-multiplicar tbody td{font-size:14px;padding:10px}
  .tabla-multiplicar{max-width:100%;margin:0 12px}
}
</style>