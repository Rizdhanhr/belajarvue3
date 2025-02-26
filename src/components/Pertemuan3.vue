<script setup>
import { reactive, ref } from 'vue';

const name = ref("Rizdhan Hernanda");
const isValidate = ref(false);
const styleSpan = reactive({
    color: 'red'
});

function changeName(e) {
    isValidate.value = false;
    if (name.value === "") {
        isValidate.value = true;
    }
}


</script>
<template>
    <div class="container mt-3">
        <h1>Pertemuan 3 {{name}}</h1>
        <h1 v-show="ok">Haloo</h1>
        <input type="text" class="form-control" v-bind:class="{ 'is-invalid': isValidate }" v-model="name" @change="changeName($event)" placeholder="Nama"/> 
        <!-- <span v-bind:style="isValidate ? styleSpan : {}"> {{ isValidate? 'This name is required.' : ''}}</span> -->
        <span v-show="isValidate" style="color:red;">This name is required.</span>
    </div>
</template>