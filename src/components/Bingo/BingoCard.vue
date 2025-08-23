<script setup>
/*
- This will be used for both editing mode and preview mode.
*/

import { ref, watch, computed } from 'vue';
import BingoSquare from './BingoSquare.vue';

const props = defineProps({
    dimensionNumber: Number,
    cardTitle: String,
    bingoSquares: [Object],
    card: Object,
    selectedSquare: Object
});

const cardDimension = ref(3);
const gridStyle = ref("grid-dim-3x3");

watch(() => props.dimensionNumber, (dimensionNumber) => {
    console.log(dimensionNumber)
    cardDimension.value = props.dimensionNumber;
})

const test = computed(() => ({
    'grid-dim-3x3': props.dimensionNumber === 3,
    'grid-dim-4x4': props.dimensionNumber === 4,
    'grid-dim-5x5': props.dimensionNumber === 5
}));

</script>

<template>
    <div class="bingo-card" :class="test">
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