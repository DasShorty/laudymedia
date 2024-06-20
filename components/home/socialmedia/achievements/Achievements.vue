<script setup lang="ts">

import Achievement from "~/components/home/socialmedia/achievements/Achievement.vue";
import axios from "axios";

const { pending, data: posts } = useFetch('http://localhost:8080/public/achievements', {
  lazy: true
})

//onMounted(() => {
//  axios.get("http://localhost:8080/public/achievements")
//      .then((response) => {
//        content = response.data;
//        console.log(content);
//        console.log(response.data);
//      })
//})

</script>

<template>

  <div class="title">
    <h3>Errungenschaften
      <hr>
    </h3>
  </div>

  <div v-if="pending">
    <p>Loading...</p>
  </div>
  <div v-else class="achievements-list">
    <Achievement v-for="achievement in posts" :image="achievement.imageRef" :text="achievement.name"></Achievement>
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

.achievements-list {
  margin-top: 5rem;
  background-color: #101010;
  border: 1px solid #2E2E2E;
}

.title {
  display: flex;
  justify-content: center;
}

@media (max-width: 1200px) {
  h3 {
    font-size: 2rem;
  }
}
</style>