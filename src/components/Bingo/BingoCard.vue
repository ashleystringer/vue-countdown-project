<script setup>
import { ref } from 'vue';
import BingoSquare from './BingoSquare.vue';

const squares = ref([
    [
        { content: "Square 1"},
        { content: "Square 2"},
        { content: "Square 3"},
    ],
    [
        { content: "Square 4"},
        { content: "Square 5"},
        { content: "Square 6"},
    ],
    [
        { content: "Square 7"},
        { content: "Square 8"},
        { content: "Square 9"},
    ]
]);


</script>

<template>
    <div class="bingo-card">
        <div class="bingo-card-row" v-for="square in squares">
            <div class="bingo-card-column" v-for="item in square">
                <BingoSquare :content="item.content"/>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .bingo-card{
        display: flex;
    }
    .bingo-card-row {
        padding: 1px;
    }
    .bingo-card-column {
        padding: 1px;
    }
</style>