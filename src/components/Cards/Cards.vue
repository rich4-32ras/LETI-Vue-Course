<script setup>
import {ref, onMounted, onUnmounted} from 'vue';
import moment from 'moment-timezone/moment-timezone';

const props = defineProps(["locate"]);
console.log(props)


const dataTime = ref(Date.now());
const interval = ref(0);

moment.tz.add([
    'America/Los_Angeles|PST PDT|80 70|0101|1Lzm0 1zb0 Op0',
    'America/New_York|EST EDT|50 40|0101|1Lz50 1zb0 Op0',
    'Asia/Tokyo|JST|-90|0|',
]);

onMounted(() => {
  interval.value = setInterval(() => (dataTime.value = Date.now()), 1000);
  console.log(dataTime)
});

onUnmounted(() => {
  clearInterval(interval.value);
});

function locateRes(locate){
  console.log(locate)
  return locate
}

function getTime(time, locate){
  var format = 'MM/DD HH:mm:ss';
  if (locate === 'Russia/Moscow'){
    return moment(time).format(format);
  }
  else {
    return moment(time).tz(locate).format(format);
  }
}
</script>

<template>
  <div>
    <slot :time="getTime(dataTime, locate)"></slot>
  </div>
</template>
