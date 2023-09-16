<script lang="ts">
import Numero from '../components/Numero.vue';
    //alert('ok');
    /*setTimeout(()=>{
    const elemento =  document.getElementById('msgH');
    if(elemento){
        elemento.innerText="Hola Juan!!";
    }
 }, 500 );*/

export default{
    components:{
        Numero
    },
    data:   () =>({
            titulo:'Hola Juan!!',
            subTitulo:'Titulo 2',
            contador:0,
            color:'',
            numeros:[] as number[]
    }),
    methods:{
        cambiarSubtitulo(){
            this.contador++;


            const modulo=this.contador % 2;
            this.color=modulo==0?'par':'impar'

            this.subTitulo='Prueba de cambio del subtitulo';
            this.numeros.push(this.contador);
        }

    } 

}
</script>
<template>
    <h1 id="msgH">{{ titulo }}</h1>
    <h2 :class="{
        'blue': color=='par',
        'red': color=='impar',
        'negrilla': color=='par'
    }">{{ subTitulo }}</h2>
    <div>
        <p v-if="color=='par'">El contador es par</p>
        <p v-else-if="color=='impar'">El contador es impar</p>
        <p v-else>El contador es cero</p>
        <ul>
            <li v-for="item of numeros">
                <Numero :numero="item"></Numero></li>
        </ul>
    </div>
    <p>{{ contador }}</p>
    <button @click="cambiarSubtitulo">Cambiar subtitulo</button>
    <input v-model="titulo">
</template>
<style scoped>
    h1{
        color: blueviolet;
        font-size: 42px;
    }
    .negrilla{
        font-weight: bolder;
    }
    .blue{
        color: blue;
    }
    .red{
        color: red;
    }
</style>