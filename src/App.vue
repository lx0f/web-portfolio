<script setup lang="ts">
import HelloCard from './components/HelloCard.vue'
import HappyCard from './components/HappyCard.vue'
import SadCard from './components/SadCard.vue'

import { ref } from 'vue'

const isHappy = ref(true)
const isStart = ref(false)
const showGhost = ref(false)

async function triggerHorror() {
  isStart.value = true
  await new Promise((resolve) =>
    setTimeout(() => {
      document.getElementsByTagName('html')[0].style.backgroundImage = "url('/mugshot-mod.png')"
      document.getElementsByTagName('html')[0].style.backgroundColor = 'black'
      isHappy.value = false
      document.getElementsByTagName('audio')[0].play()
      alert("It's in the walls, it's in the walls, it's in the walls, it's in the walls")
      alert('look behind you')
      resolve(null)
    }, 3000)
  )
  await new Promise((resolve) => setTimeout(resolve, 5000))
  document.getElementsByTagName('audio')[1].play()
  await new Promise((resolve) => setTimeout(resolve, 500))
  showGhost.value = true
  await new Promise((resolve) =>
    setTimeout(() => {
      showGhost.value = false
      resolve(null)
    }, 6666)
  )
}
</script>

<template>
  <HelloCard v-if="!isStart">
    <button id="button" @click="triggerHorror()">Click Me!!</button>
  </HelloCard>
  <component v-if="isStart" :is="isHappy ? HappyCard : SadCard" />
  <div v-if="showGhost" class="ghost">
    <div class="col"></div>
    <div class="col">
      <div class="wrap">
        <h3>Do you like me?</h3>
        <p>i like the mud and how it'll look on your face flat on the floor</p>
      </div>
    </div>
  </div>
  <audio id="audio_ambience" src="/ambience.mp3"></audio>
  <audio id="audio_scream" src="/scream.mp3"></audio>
</template>

<style scoped>
.wrap {
  display: flex;
  flex-direction: column;
  margin: auto;
}
.col {
  width: 100%;
  display: flex;
  align-content: center;
}
.ghost {
  background-image: url('/ghost.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  height: 100vh;
  width: 100vw;
  position: absolute;
  display: flex;
  font-size: x-large;
  font-family: cursive;
  color: maroon;
  top: 0;
  left: 0;
}
</style>
