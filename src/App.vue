<script setup lang="ts">
import HelloCard from "./components/HelloCard.vue";
import HappyCard from "./components/HappyCard.vue";
import SadCard from "./components/SadCard.vue";

import { ref } from "vue";

const isHappy = ref(true);
const isStart = ref(false);

function triggerHorror() {
  isStart.value = true;
  setTimeout(() => {
  document.getElementsByTagName("html")[0].style.backgroundImage = "url('/mugshot-mod.png')";
  document.getElementsByTagName("html")[0].style.backgroundColor = "black";
  isHappy.value = false;
  document.getElementsByTagName("audio")[0].play();
  alert("It's in the walls, it's in the walls, it's in the walls, it's in the walls");
  alert("look behind you");
}, 3000);
}
</script>

<template>
  <HelloCard v-if="!isStart" >
    <button id="button" @click="triggerHorror();">Start</button>
  </HelloCard>
  <component v-if="isStart" :is="isHappy ? HappyCard : SadCard" />
  <audio id="audio" src="/ambience.mp3"></audio>
</template>

<style scoped>
</style>
