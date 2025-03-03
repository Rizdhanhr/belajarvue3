<script setup>
import { inject } from 'vue';


defineProps(['text']);
const nama = inject('nama', 'Not Found');
</script>
<template>
    <h1>Hallo Component C {{text}} {{nama}}</h1>
</template>