<template>
  <div>
    <h1>Seleccion multiple</h1>
     <multiselect  v-model="value" :options="options" multiple placeholder="Selecciona uno o varios"></multiselect>
      <div class="decor">
        <span class="ornament ornament-left" aria-hidden></span>
        <span class="decor-text"></span>
        <span class="ornament ornament-right" aria-hidden></span>
      </div>
      <div class="seleccionadas" v-if="value && value.length">
        <h3>Seleccionadas ({{ value.length }})</h3>
        <ul>
          <li v-for="(valor, index) in value" :key="index">{{ valor }}</li>
        </ul>
      </div>
  </div>
  
</template>

<script>
import Multiselect from 'vue-multiselect'
import 'vue-multiselect/dist/vue-multiselect.css'
export default {
  name: "SeleccionMultiple",
  components: { Multiselect },
  data() {
    return {
      // para selección múltiple usar un array vacío por defecto
      value: [],
      options: ['Elemento1', 'Elemento2', 'Elemento3', 'Elemento4', 'Elemento5', 'Elemento6', 'Elemento7', 'Elemento8', 'Elemento9', 'Elemento10'   ]
    };
  }
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Mountains+of+Christmas:wght@400;700&family=Poppins:wght@400;600&display=swap');

.seleccion-multiple-container {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 28px 12px 48px;
  background: radial-gradient(circle at 10% 10%, #ffefef 0%, transparent 15%),
              linear-gradient(180deg,#7f1d1d 0%, #7c2d12 40%, #064e3b 100%);
  min-height: 100vh;
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
}

/* Snow layer */
.seleccion-multiple-container::after {
  content: '';
  position: absolute;
  left: 0;
  top: -20%;
  width: 200%;
  height: 160%;
  background-image: radial-gradient(#ffffff33 1px, transparent 1px);
  background-size: 12px 12px;
  pointer-events: none;
  animation: snow 14s linear infinite;
  opacity: 0.9;
}

@keyframes snow {
  0% { transform: translateY(-10%) translateX(0); }
  100% { transform: translateY(30%) translateX(-30%); }
}

.card {
  width: 100%;
  max-width: 860px;
  background: linear-gradient(180deg, rgba(255,255,255,0.06), rgba(255,255,255,0.02));
  border-radius: 18px;
  box-shadow: 0 12px 40px rgba(2,6,23,0.45);
  padding: 26px;
  border: 2px solid rgba(255,255,255,0.06);
  position: relative;
  z-index: 2;
}

.title {
  margin: 0 0 6px 0;
  font-family: 'Mountains of Christmas', cursive;
  font-size: 2rem;
  color: #fff7f7;
  text-align: center;
  text-shadow: 0 2px 8px rgba(0,0,0,0.6);
}

.decor {
  display:flex;
  align-items:center;
  justify-content:center;
  gap: 12px;
  margin-bottom: 12px;
}

.decor-text{
  color: #fff;
  font-family: 'Poppins', sans-serif;
  font-weight: 600;
  background: linear-gradient(90deg,#f97316,#ef4444);
  padding: 6px 12px;
  border-radius: 999px;
  box-shadow: 0 6px 18px rgba(0,0,0,0.35);
}

.ornament{
  width: 18px;
  height: 18px;
  border-radius: 50%;
  box-shadow: inset -3px -3px 6px rgba(0,0,0,0.25), 0 4px 12px rgba(0,0,0,0.35);
  position: relative;
}
.ornament::after{
  content: '';
  position: absolute;
  top: 3px;
  left: 4px;
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: rgba(255,255,255,0.7);
  filter: blur(0.5px);
}
.ornament-left{ background: radial-gradient(circle at 30% 30%, #fff 0%, #ef4444 30%, #b91c1c 100%);} /* red */
.ornament-right{ background: radial-gradient(circle at 30% 30%, #fff 0%, #34d399 30%, #065f46 100%);} /* green */

.custom-multiselect {
  width: 100%;
}

/* Tweak vue-multiselect styles to match theme */
.custom-multiselect .multiselect__input,
.custom-multiselect .multiselect__tags,
.custom-multiselect .multiselect__single {
  min-height: 52px;
  padding: 10px 14px;
  border-radius: 12px;
  background: linear-gradient(180deg, rgba(255,255,255,0.03), rgba(255,255,255,0.01));
  border: 1px solid rgba(255,255,255,0.06);
  color: #fff;
}

.custom-multiselect .multiselect__tag {
  background: linear-gradient(90deg,#ef4444 0%, #10b981 100%);
  color: #fff;
  border-radius: 999px;
  padding: 6px 12px;
  margin-right: 8px;
  font-size: 0.9rem;
  font-weight: 700;
  box-shadow: 0 6px 20px rgba(0,0,0,0.45);
}

.custom-multiselect .multiselect__option--highlight,
.custom-multiselect .multiselect__option--selected {
  background: rgba(255,255,255,0.04);
  color: #fff;
}

.custom-multiselect .multiselect__option {
  color: #fff;
}

.seleccionadas {
  margin-top: 16px;
}

.seleccionadas h3 {
  margin: 0 0 8px 0;
  font-size: 1rem;
  color: #fff;
}

.seleccionadas ul {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.seleccionadas li {
  background: linear-gradient(180deg,#064e3b,#10b981);
  color: #fff;
  padding: 8px 12px;
  border-radius: 999px;
  font-weight: 700;
  font-size: 0.9rem;
  box-shadow: 0 6px 18px rgba(0,0,0,0.45);
}

/* small twinkle on the card edges */
.card::before, .card::after{
  content: '';
  position: absolute;
  width: 12px;
  height: 12px;
  border-radius: 50%;
  top: 14px;
  left: 14px;
  background: radial-gradient(circle at 30% 30%, #fff, transparent 40%);
  box-shadow: 0 0 18px rgba(255,255,255,0.12);
  opacity: 0.9;
}
.card::after{ left: auto; right: 14px; background: radial-gradient(circle at 30% 30%, #fff, transparent 40%); }

/* Responsive */
@media (max-width: 520px) {
  .card { padding: 18px; }
  .title { font-size: 1.6rem; }
  .decor-text{ padding: 5px 10px; }
}

</style>