<script>
export default {
  inheritAttrs: false,
};
</script>

<script setup>
import { ref, Teleport, Transition, watchEffect } from 'vue';
import css from './Popup.module.css';

const emit = defineEmits(['close']);
const props = defineProps(['open', 'duration']);

const TIME_OUT = 5000;
const timeOut = ref(0);

watchEffect(() => {
    if (props.open === false) return;
    timeOut.value = setTimeout(() =>emit('close'), props.duration || TIME_OUT)
});

function closePopup(){
    clearTimeout(timeOut.value);
    emit('close');
}


</script>

<template>
    <Teleport to="#popup">
        <Transition> 
            <div :class="css.popup" v-if="open">
                <div :class="css.popup__header">
                    <div :class="css.popup__text"><slot></slot></div>
                    <button :class="css.btn__exit" @click="closePopup()">&times;</button>
                </div>
            </div>
        </Transition>
    </Teleport>
</template>

<style scoped>

.v-enter-active,
.v-leave-active {
  transition: 200ms;
}

.v-enter-from {
  opacity: 0;
  transform: translateY(-100%);
}

.v-leave-to {
  opacity: 0;
  transform: translateX(-100%);
}
</style>