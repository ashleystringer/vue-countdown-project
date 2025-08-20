<script setup>
import DateDisplay from './components/DateDisplay.vue';
import Calendar from './components/Calendar.vue';
import BingoCard from './components/Bingo/BingoCard.vue';
import BingoCardCreator from './components/Bingo/CardCreator/BingoCardCreator.vue';

/*
Should a dynamic variable be created here and used as a prop in DateDisplay and Calendar?
Would this prop be pass by reference or pass by value?
Answer - props possess one-way data flow, so you'd need to emit them from the children
- DateDisplay should be able to chance it, but probably not Calendar.
*/


</script>

<template>
  <div id="app">
    <DateDisplay/>
    <Calendar/>
    <br/>
    <BingoCardCreator/>
    <!--<BingoCard/>-->
    
  </div>
</template>

<style scoped>
</style>
