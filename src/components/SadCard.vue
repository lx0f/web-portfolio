<script setup lang="ts"></script>
<template>
  <div class="card">
    <h1>Luth Andyka</h1>
    <p>Hi, I'm a full-stack developer from Singapore.</p>
    <ul>
      <li>
        Phone number: <a href="https://wa.me/6592229652">+65 92229652</a> <small>(whatsapp)</small>
      </li>
      <li>
        Email: <a href="mailto:luthandyka.business@gmail.com">luthandyka.business@gmail.com</a>
      </li>
      <li>Github: <a href="https://github.com/lx0f">lx0f</a></li>
    </ul>
  </div>
</template>
<style scoped>
a {
  color: white;
  text-decoration: none;
  transition: all 0.2s ease-in-out;
}

a:hover {
  color: green;
  font-size: 16em;
  font-weight: 900;
  transform: scale(1.1);
}

.card {
  display: flex;
  flex-direction: column;
  background-color: maroon;
  color: black;
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
