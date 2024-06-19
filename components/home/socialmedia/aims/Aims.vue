<script lang="ts">
import Aim from "./Aim.vue";

export default {
  components: {
    Aim
  }
}

</script>

<template>

  <div class="title">
    <h3>Meine Ziele
      <hr>
    </h3>
  </div>
  <div class="aims-list">

    <div class="left-side">
      <Aim icon="https://cdn.laudymedia.de/twitch.png" count-type="FOLLOWER" platform="twitch" bar-color="#48247D"></Aim>
      <Aim icon="https://cdn.laudymedia.de/tiktok.png" count-type="FOLLOWER" platform="tiktok" bar-color="#8D1A30"></Aim>
    </div>

    <div class="right-side">
      <Aim icon="https://cdn.laudymedia.de/youtube.png" count-type="ABONNENTEN" platform="youtube" bar-color="#A60000"></Aim>
      <Aim icon="https://cdn.laudymedia.de/twitter.png" count-type="FOLLOWER" platform="twitter" bar-color="#249EF1"></Aim>
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