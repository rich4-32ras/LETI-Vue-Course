
<script setup>
import {ref} from 'vue';
const counter = ref(0);
</script>

<template>
	<h2>Counter</h2>
    <button @click="counter++">counter {{counter}}</button>
</template>

<style scoped>
h2 {
	text-align: center;
	color: rgb(13, 13, 14);
}

button{
	margin: 0 auto;
	display: block;
	font-family: 'Comfortaa', cursive;
	border: 0;
	border-radius: 5px;
	text-align: center;
	font-size: 50;
	color: azure;
	background-color: rgb(55, 55, 55);
	padding: 16px;
	
	
}

button:hover {
	background-color: rgb(119, 118, 118);
	box-shadow: 10px 10px #333;
	transition: 0.2s;
}
</style>