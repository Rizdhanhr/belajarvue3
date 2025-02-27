<script setup>
import { reactive, ref, watch } from 'vue';

const name = ref("Rizdhan Hernanda");
const isValidate = ref(false);
const styleSpan = reactive({
    color: 'red'
});

const questions = ref("");

function changeName(e) {
    isValidate.value = false;
    if (name.value === "") {
        isValidate.value = true;
    }
} 

function enterAction() {
    alert("Enter Ditekan");
}

watch(questions, async (newQuestions,oldQuestions) => {
    console.log('Pertanyaan Lama '+oldQuestions);
    console.log('Pertanyaan Baru '+newQuestions);
});

</script>
<template>
    <div class="container mt-3">
        <h1>Pertemuan 3 {{name}}</h1>
        <h1 v-show="ok">Haloo</h1>
        <input type="text" class="form-control" v-bind:class="{ 'is-invalid': isValidate }" v-model="name" @change="changeName($event)" placeholder="Nama"/> 
        <!-- <span v-bind:style="isValidate ? styleSpan : {}"> {{ isValidate? 'This name is required.' : ''}}</span> -->
        <span v-show="isValidate" style="color:red;">This name is required.</span>
    </div>
    <ul>
        <li v-for="n in 10" :key="n">{{n}}</li>
    </ul>

    <div class="container mt-3">
        <h1>Test Event Vue</h1>
        <button @keyup.enter="enterAction" class="btn btn-primary">Testing</button>
    </div>

     <div class="container mt-3">
        <h1>Test Watcher Vue</h1>
        <input class="form-control" type="text" v-model.lazy="questions" placeholder="Masukkan Pertanyaan">
    </div>
</template>