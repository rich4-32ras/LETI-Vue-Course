<script setup>
import {ref} from 'vue';
import Popup from './components/Popup/Popup.vue';
import css from './App.module.css'
const isOpen = ref(false);
</script>

<template>
  <div :class="css.container">
    <button :class="css.btn" @click="isOpen = !isOpen">magick clik</button>
  </div>
  <Popup :open="isOpen" @close="isOpen = false">Всплывашка</Popup>
</template>

<style scoped></style>