<script setup>
    defineProps({
        content: String
    })
</script>

<template>
    <div class="bingo-square">{{ content }}</div>
</template>

<style scoped>
    .bingo-square{
        border: 1px solid red;
        height: 55px;
        width: 55px;
        overflow: scroll;
    }
</style>