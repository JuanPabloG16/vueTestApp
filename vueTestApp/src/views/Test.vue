<script setup lang="ts">
import {ref} from "vue";
import Numero from '../components/Numero.vue';

const contador = ref<number>(0);
const numeros=ref<Array<number>>([]);
const logListaNumeros = ref<number>(0);
    

function incrementar():void{
    contador.value++;
}
function generarListaNumero(): void{
    for (let index=0; index<logListaNumeros.value;index++){
        numeros.value.push(index);
    }
}

</script>
<template>
<h1>Contador: {{ contador }}</h1>
<button @click="incrementar">Incrementar</button>
<br>
<form>
    <input type="number" v-model="logListaNumeros">
    <button type="button" @click="generarListaNumero">Generar</button>
</form>
<div>
    <ul>
       <li v-for="item in numeros">
    <!-- {{ numero }} -->
    <Numero :numero="item"></Numero>

        </li> 
    </ul>
</div>
</template>
<style scoped></style>