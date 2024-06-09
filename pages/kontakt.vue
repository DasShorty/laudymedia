<script setup lang="ts">

import WriteContactContainer from "~/components/contact/WriteContactContainer.vue";
import ThumbnailComponent from "~/components/home/ThumbnailComponent.vue";
</script>

<template>
  <Header></Header>
  <ThumbnailComponent></ThumbnailComponent>
  <main>

    <div class="container">

      <div class="contact-title">
        <span>Kontakt</span>
      </div>

      <div class="contact-info">
        <WriteContactContainer></WriteContactContainer>
      </div>

    </div>

  </main>
  <Footer></Footer>
</template>

<style scoped>

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.contact-title span {
  text-transform: uppercase;
  color: #1A1A1A;
  font-size: 8rem;
  font-family: "ZenDots", sans-serif;
}

.contact-info {
  margin-top: -6rem;
}

</style>