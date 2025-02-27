<script setup>
import { reactive, watch, ref } from 'vue';
import InputText from './InputText.vue';
import ButtonCounter from './ButtonCounter.vue';

const data = reactive({
    name: "",
    kelas: ""
});

const counter = ref(0);

watch(()=> data.name, async (newVal, oldVal) => {
    console.log(newVal);
});


</script>
<template>
    <div class="container mt-3">
        <h1>Hello World Coeg {{data.name}}</h1>
        <InputText v-model.lazy="data.name" title="Nama"/>
        <InputText title="Kelas"/>
    </div>
    <ButtonCounter :counter="counter"/>
</template>