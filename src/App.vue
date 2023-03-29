<script setup>
import css from './App.module.css'
import { ref } from 'vue';

const  text = ref("");
const cards = ref([{msg: "деревня", inf: "за городом"}, {msg: "деревяшки", inf: "из них строят дома"}, {msg: "дом", inf: "можно жить и есть"}]);

</script>

<template>
    <h1 :class="css.myClass" >//HW2//</h1>
    <input :class="css.myInput" v-model="text"/>

    <template  v-for="card in cards">
      
      <div :class="css.myRectangleCard" v-if="card.msg.includes(text)">
        <h2>{{ card.msg }}</h2>
        <p>{{ card.inf }}</p>
      </div>
    
    </template>
</template>
