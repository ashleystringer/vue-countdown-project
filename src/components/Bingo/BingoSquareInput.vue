<script setup>
import { ref, reactive, watch, computed } from 'vue';

const props = defineProps({
    card: Object,
    selectedSquare: Object
}); 

/*
- Form
    - Square input
    - User-created tags (optional)
    - Linked to its corresponding square
    - Ability to move to another square from either directions
    - Ability to switch squares by user clicking on a specific square
*/
</script>

<template>
    <form>
        <input :value="text" @input="onInput" placeholder="Type here"></input>
        <div>Tag system</div>
        <!-- Orientation -->
    </form>
</template>

<style scoped>
</style>