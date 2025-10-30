<template>

    <div>
       
       
        <ul id="menu">
             <li v-for="num in numeros" :key="num">
                <router-link :to="'/tablamultiplicar/'+num">tabla multiplicar {{num}}</router-link>
               
            </li>
        </ul>
    </div>
    

  
</template>

<script>
export default {
name:"MenuTablaMultiplicar",
data(){
    return{
        numeros:[]
    };
},
mounted(){
        this.NumeroAleatorio();
},
methods:{
        NumeroAleatorio(){
            for(let i=0;i<5;i++){
                let numeroAleatorio=Math.floor(Math.random()*100)+1;
                this.numeros.push(numeroAleatorio);
            }
        }
    }
}
</script>

<style>

</style>