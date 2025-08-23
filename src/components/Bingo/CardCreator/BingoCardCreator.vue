<script setup>
import { ref, reactive } from 'vue';
import BingoCard from '../BingoCard.vue';
import BingoSquareInput from '../BingoSquareInput.vue';

const card = reactive({});
const selectedSquare = reactive({});
/*
- Three options for dimensions (3 x 3, 4 x 4, 5 x 5) [PRIORITY]
- Directly edit the empty squares of the empty bingo card [PRIORITY]
- Allow the user to update squares using a form to the left of the card
- Allow the user to change with square to update in the form
- Allow the user to add tags to individual squares 
- Allow the user to randomize the content of all squares or individual squares
- REQUIREMENTS - 
    ** Need to change the dimensions of the generated bingo card using the select element [PRIORITY]
    ** Need to submit card and square information to the BingoSquare component as props
    ** Need to sync the data of the bingo square with the form [PRIORITY]
    ** Sync the data of the general bingo card and the form data

*/

const dimensionNumber = ref(4);

function selectDimension(e){
    console.log(e.target.value);

    if(!e.target.value) return; 

    switch(e.target.value){
        case "dim-3x3":
            dimensionNumber.value = 3;
            break;
        case "dim-4x4":
            dimensionNumber.value = 4;
            break;
        case "dim-5x5":
            dimensionNumber.value = 5;
            break;
    }
}
</script>

<template>
    <div>
        <div>
            <select @change="selectDimension">
                <option>Select Dimensions</option>
                <option value="dim-3x3">3 x 3</option>
                <option value="dim-4x4">4 x 4</option>
                <option value="dim-5x5">5 x 5</option>
            </select>
        </div> 
        <div>
            <BingoSquareInput/>
            <BingoCard :dimensionNumber="dimensionNumber"/>
        </div>      
    </div>
</template>

<style scoped>
</style>