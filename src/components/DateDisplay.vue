<script setup>
import { ref, reactive, onMounted, onUnmounted } from 'vue'


const timeDifference = ref(0)
const displayedTime = ref(0)

function updateTimer(){
    let intervalId;
    const targetDate = new Date("October 29, 2025");

    let now = new Date().getTime();
    timeDifference.value = targetDate - now;

    onMounted(() => intervalId = setInterval(() => {
        now = new Date().getTime()
        let difference = targetDate - now;

        const days = Math.floor(difference / 86400000);
        const hours = Math.floor((difference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        const minutes = Math.floor((difference % (1000 * 60 * 60)) / (1000 * 60));
        const seconds = Math.floor((difference % (1000 * 60)) / 1000);

        timeDifference.value = difference;
        displayedTime.value = `${days}:${hours}:${minutes}:${seconds}`;
    }, 1000));

    /*
    Idea
        - Check the date (probably using "let now = new Date().getTime();")
        - If the date is different from what it was previously
            - Flag it in a dynamic variable
            - And use this flag to change the start and end dates of the first item object in Calendar    
    */

    onUnmounted(() => clearInterval(intervalId));
}


updateTimer()

</script>

<template>
   <div>{{ displayedTime }}</div>

</template>

<style scoped></style>