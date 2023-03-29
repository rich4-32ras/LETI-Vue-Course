<script setup>
import { watchEffect, reactive, ref } from 'vue';


const data = ref(new Date().toLocaleTimeString());

watchEffect(() => {
    setInterval(() => {
        data.value = new Date().toLocaleTimeString();
    }, 1000)
})

</script>

<template>
    <div>
        <h2 style="text-align: center; color:#333">{{data}}</h2>
    </div>
</template>

<style scoped></style>