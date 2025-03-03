<script setup>
import { ref, provide } from 'vue';
import ComponentB from './ComponentB.vue';
import ComponentC from './ComponentC.vue';
import Cards from './Cards.vue';
const text = ref("Hallo Indonesia");
provide('nama', 'Rizdhan Hernanda');
</script>
<template>
    <div class="container">
        <h1>Halloo Component A</h1>
        <ComponentB :text="text"/>
        <ComponentC/>
    </div>
    <div class="container mt-3">
        <Cards :title="text">
            <div class="mb-3">
                <label class="form-label">Nama Pelanggan</label>
                <input type="text" class="form-control"/>
            </div>
        </Cards>
    </div>
</template>