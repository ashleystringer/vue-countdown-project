<script setup>
    defineProps({
        content: String
    })
    /*
        Create editing mode
    */
</script>

<template>
    <div class="bingo-square">{{ content }}</div>
</template>

<style scoped>
    .bingo-square{
        border: 1px solid red;
        height: 65px;
        width: 65px;
        overflow: scroll;
    }
</style>