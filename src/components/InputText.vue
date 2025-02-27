<script setup>
defineProps(['title','modelValue']);
defineEmits(['update:modelValue']);
</script>
<template>
    <div class="mb-3">
        <label>{{title}}</label>
        <input type="text" class="form-control" :value="modelValue" @change="$emit('update:modelValue',$event.target.value)" :placeholder="'Masukkan '+title"/>
    </div>
</template>