<script setup lang="ts">

import Achievement from "~/components/home/socialmedia/Achievement.vue";
</script>

<template>

  <div class="title">
    <h3>Errungenschaften</h3>
    <hr>
  </div>

  <div class="achievements-list">
    <Achievement image="https://cdn.dasshorty.de/twitch.png" text="Twitch Affiliate 2024"></Achievement>
    <Achievement image="https://cdn.dasshorty.de/twitch.png" text="Twitch Affiliate 2024"></Achievement>
  </div>

</template>

<style scoped>

h3 {
  text-transform: uppercase;
  font-size: 2.625rem;
}

hr {
  border-radius: 1rem;
  border-color: var(--hr-color);
}

.achievements-list {
  background-color: #101010;
  border: 1px solid #2E2E2E;
}

.title {
  text-align: center;
}

</style>