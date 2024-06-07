<script setup lang="ts">

import Aim from "~/components/home/socialmedia/aims/Aim.vue";
</script>

<template>

  <div class="title">
    <h3>Meine Ziele
      <hr>
    </h3>
  </div>
  <div class="aims-list">

    <div class="left-side">
      <Aim icon="https://cdn.dasshorty.de/twitch.png" count-type="FOLLOWER" :current-count='52'
           :final-count='100' bar-color="#48247D"></Aim>
      <Aim icon="https://cdn.dasshorty.de/twitch.png" count-type="FOLLOWER" :current-count='70'
           :final-count='100' bar-color="#8D1A30"></Aim>
    </div>

    <div class="right-side">
      <Aim icon="https://cdn.dasshorty.de/twitch.png" count-type="ABONNENTEN" :current-count='42'
           :final-count='100' bar-color="#A60000"></Aim>
      <Aim icon="https://cdn.dasshorty.de/twitch.png" count-type="FOLLOWER" :current-count='220'
           :final-count='1000' bar-color="#249EF1"></Aim>
    </div>

  </div>

</template>

<style scoped>

h3 {
  text-transform: uppercase;
  font-size: 2.625rem;
}

hr {
  margin-top: -0.3rem;
  border-radius: 1rem;
  border-color: var(--hr-color);
}

.title {
  display: flex;
  justify-content: center;
}

.aims-list {
  display: flex;
  flex-direction: row;
  margin-top: 3rem;
}

</style>