<script setup>

defineProps(['title']);

</script>
<template>
    <div class="card">
        <div class="card-header">
            {{ title }}
        </div>
        <div class="card-body">
            <slot/>
        </div>
    </div>
</template>