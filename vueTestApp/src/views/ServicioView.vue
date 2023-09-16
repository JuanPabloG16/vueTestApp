<script setup lang="ts">
import {ref} from 'vue';
import axios from 'axios';

interface Producto{
    category:string;
    description:string;
    id:number;
    image:string;
    price:number;
    raiting:{
        rate:number;
        count:number;
    };
    title:string;
};

const products = ref<Array<Producto>>([]);

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
    <div v-for="item of products">
    <img :src="item.image" alt="Producto"></div>
</template>
<style scoped>
img{
    width: 18px;

}
</style>