
<script setup>
    import { ref, onMounted, onUnmounted } from 'vue';
    const time = ref(Date.now());
    const timeIntervalId = ref(0);

    onMounted(() => {
    setInterval(() => {
        time.value = Date.now();
    },100);
    });

    onUnmounted(() => {
    clearInterval(timeIntervalId.value)
    });
</script>

<template>
    <div>{{ time }}</div>
</template>
