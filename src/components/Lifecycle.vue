<script setup>
import { onMounted, onUpdated, ref } from 'vue';


const name = ref("Rizdhan");


onMounted(() => {
    console.log('mounting');
    name.value+=" Hernanda";
});

onUpdated(() => {
    alert('diperbarui');
});

function changeName(){
    name.value = "RHR";
}


</script>

<template>
    <h1>Hello World {{name}}</h1>
    <button type="button " class="btn btn-primary" @click="changeName">Click</button>
</template>