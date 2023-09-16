<script setup lang="ts">
import {ref} from 'vue';
import axios from 'axios';

const products = ref<Array<any>>([]);

axios.get('https://fakestoreapi.com/products', {
    headers:{
        Authorization:'123456',
        'keyAuth':'test1236'
    }
})
.then(response=>{
    console.log(response)
    products.value = response.data;
})
.catch(error=>{
console.log(error);
alert('Error al consumir el servicio');
})
.finally(()=>{
    console.log('Se finalizo la consulta del servicio');
});


</script>
<template>

</template>
<style scoped></style>