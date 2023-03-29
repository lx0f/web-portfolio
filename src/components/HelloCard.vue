<script setup lang="ts">

</script>
<template>
<div class="card">
    <h1>Hello!</h1>
    <p>Thank you for coming to my website.</p>
    <p>I not speak english well but I appreciate your coming 🥰🥰🥰</p>
    <slot></slot>
</div>
</template>
<style scoped>
a {
  color: white;
  text-decoration: none;
  transition: all 0.2s ease-in-out;
}

a:hover {
  color: yellow;
  font-size: 16em;
  font-weight: 900;
  transform: scale(1.1);
}

.card {
  display: flex;
  flex-direction: column;
  background-color: salmon;
  color: white;
  text-align: center;
  margin: auto;
  padding: 2rem;
  border-radius: 1rem;
}
ul {
  list-style-type: none;
  padding: 0;
}
h1 {
  font-size: 2.5rem;
  font-weight: 700;
  margin-bottom: 0.5rem;
}
</style>