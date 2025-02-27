<script setup>
defineProps({
    counter: {
        default: 0
    }
});
</script>
<template>
    <div class="container mt-3">
        <h1>{{ counter }}</h1>
        <button type="button" class="btn btn-primary">Counter++</button>
    </div>
</template>