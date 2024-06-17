<script lang="ts">
import axios from "axios";
import Aim from "./Aim.vue";

export default {
  data() {
    return {
      twitter: {'currentAmount': 20, 'aimAmount': 20},
      youtube: {'currentAmount': 20, 'aimAmount': 20},
      twitch: {'currentAmount': 20, 'aimAmount': 20},
      tiktok: {'currentAmount': 20, 'aimAmount': 20},
    }
  },
  components: {
    Aim
  },
  mounted() {
    axios.get("http://localhost:8080/public/aims?platform=twitter").then((res) => {
      this.twitter = res.data;
    });
    axios.get("http://localhost:8080/public/aims?platform=youtube").then((res) => {
      this.youtube = res.data;
    });
    axios.get("http://localhost:8080/public/aims?platform=twitch").then((res) => {
      this.twitch = res.data;
    });
    axios.get("http://localhost:8080/public/aims?platform=tiktok").then((res) => {
      this.tiktok = res.data;
    });
  },
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
      <Aim icon="https://cdn.laudymedia.de/twitch.png" count-type="FOLLOWER" :current-count='twitch.currentAmount'
           :final-count='twitch.aimAmount' bar-color="#48247D"></Aim>
      <Aim icon="https://cdn.laudymedia.de/tiktok.png" count-type="FOLLOWER" :current-count='tiktok.currentAmount'
           :final-count='tiktok.aimAmount' bar-color="#8D1A30"></Aim>
    </div>

    <div class="right-side">
      <Aim icon="https://cdn.laudymedia.de/youtube.png" count-type="ABONNENTEN" :current-count='youtube.currentAmount'
           :final-count='youtube.aimAmount' bar-color="#A60000"></Aim>
      <Aim icon="https://cdn.laudymedia.de/twitter.png" count-type="FOLLOWER" :current-count='twitter.currentAmount'
           :final-count='twitter.aimAmount' bar-color="#249EF1"></Aim>
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