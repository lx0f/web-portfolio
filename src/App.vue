<script setup lang="ts">
import HappyCard from "./components/HappyCard.vue";
import SadCard from "./components/SadCard.vue";

import { ref } from "vue";

const isHappy = ref(true);

function simulateClick() {
  const button = document.getElementById("button");
  const event = new MouseEvent('click', {
    view: window,
    bubbles: true,
    cancelable: true
  });
  button?.dispatchEvent(event);
}
simulateClick();

setTimeout(() => {
  document.getElementsByTagName("html")[0].style.backgroundImage = "url('/mugshot-mod.png')";
  document.getElementsByTagName("html")[0].style.backgroundColor = "black";
  isHappy.value = false;
  alert("It's in the walls, it's in the walls, it's in the walls, it's in the walls");
  alert("look behind you");
}, 3000);
</script>

<template>
  <component :is="isHappy ? HappyCard : SadCard" />
</template>

<style scoped>
</style>
