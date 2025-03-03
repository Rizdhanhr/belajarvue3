<script setup>
import ComponentC from './ComponentC.vue';
const props = defineProps(['text']);

</script>
<template>
    <h1>Hallo Component B {{text}}</h1>
    <ComponentC/>
</template>     