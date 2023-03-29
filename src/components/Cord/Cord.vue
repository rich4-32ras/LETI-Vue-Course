<script setup>
import { reactive } from 'vue';

const cordXY = reactive({
    cordX: 0,
    cordY: 0,
}) 
</script>

<template>
    <div>
        <h2>Cord</h2>
        <h3 id="rectangle" @mousemove="cordXY.cordX = $event.clientX,cordXY.cordY = $event.clientY "></h3>
        <h3 id="output">X:{{cordXY.cordX - 205}} -Y:{{cordXY.cordY - 531}}</h3>
    </div>
</template>

<style scoped>
h2 {
    text-align: center;
    color:#0f0f0f
}

#output{
    text-align: center;
}

#rectangle {
    margin:auto;
    width:500px;
    height:100px;
    background:rgb(44, 44, 44);
}
</style>