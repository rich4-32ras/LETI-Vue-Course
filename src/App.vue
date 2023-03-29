
<script setup>
  import Cord from './components/Cord/Cord.vue';
import Counter from './components/Counter/Counter.vue';
  import Time from './components/Time/Time.vue';
</script>

<template>
  <h1>Настоящее время</h1>
  <Time></Time>
  <Counter></Counter>
  <Cord></Cord>
</template>

<style scoped>
h1 {
  color: rgb(13, 13, 14);
  text-align: center;  
}

</style>