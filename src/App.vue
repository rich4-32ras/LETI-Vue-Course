<script setup>

import Cards from './components/Cards/Cards.vue';
import css from './components/Cards/Card.module.css';
import {ref} from 'vue';

const cards = ref([
  {locate: "America/New_York"},
  {locate: "America/Los_Angeles"},
  {locate: "Russia/Moscow"},
  {locate: "Asia/Tokyo"},
]);

const inputLocate = ref("");

function checkNesting(locate){
  return locate.toLowerCase().includes(inputLocate.value.toLowerCase());
}

</script>


<template>

  <h1 :class="css.myClass" >//HW3//</h1>
  <input v-model="inputLocate"/>

  <template v-for="({locate}) in cards">
      <Cards v-if="checkNesting(locate)" v-slot="time" :locate="locate">
        <h2>{{ locate }}</h2>
        <p>{{ time.time }}</p>
      </Cards>
  </template>
</template>

<style></style>

