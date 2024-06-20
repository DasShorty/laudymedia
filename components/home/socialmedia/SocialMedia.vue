<script setup lang="ts">

import Achievements from "~/components/home/socialmedia/achievements/Achievements.vue";
import Aims from "~/components/home/socialmedia/aims/Aims.vue";
</script>

<template>

  <div class="social-media-container">

    <span>Social Media</span>
    <div class="achievements">
      <Achievements></Achievements>
    </div>
    <div class="aims">
      <Aims></Aims>
    </div>

  </div>

</template>

<style scoped>

.social-media-container {
  margin-top: 6rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.social-media-container span {
  font-size: 8rem;
  color: #171717;
  font-family: "ZenDots", sans-serif;
  text-transform: uppercase;
}

.achievements {
  margin-top: -6rem;
}

.aims {
  margin-top: 4rem;
  margin-bottom: 10rem;
}

@media (max-width: 1200px) {
  .social-media-container span {
    font-size: 6rem;
  }
}

@media (max-width: 900px) {
  .social-media-container span {
    font-size: 4rem;
  }
  .achievements {
    margin-top: -3.5rem;
  }
}

@media (max-width: 630px) {
  .social-media-container span {
    font-size: 3rem;
  }
  .achievements {
    margin-top: 0;
  }
}

@media (max-width: 460px) {
  .social-media-container span {
    font-size: 2.7rem;
  }
}

</style>