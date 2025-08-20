<script setup>
import { ref, watch } from 'vue';
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

const props = defineProps({
    dimensionNumber: Number,
    cardTitle: String,
    bingoSquares: [Object]
});

const cardDimension = ref(3);
const gridStyle = ref("grid-dim-3x3");

watch(() => props.dimensionNumber, (dimensionNumber) => {
    console.log(dimensionNumber)
    cardDimension.value = props.dimensionNumber;
})

</script>

<template>
    <div class="bingo-card" :class="{gridStyle}">
        <div class="bingo-card-row" v-for="n in cardDimension">
            <div class="bingo-card-column" v-for="n in cardDimension">
                <BingoSquare/>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .bingo-card{
        display: grid;
    }
    .grid-dim-3x3{
        grid-template-columns: repeat(3, 0fr);
    }
    .grid-dim-4x4{
        grid-template-columns: repeat(4, 0fr);
    }
    .grid-dim-5x5{
        grid-template-columns: repeat(5, 0fr);
    }
    .bingo-card-row {
        padding: 0px;
    }
    .bingo-card-column {
        padding: 0px;
    }
</style>