<script setup lang="ts">

import HeaderComponent from "~/components/header/Header.vue";
import ThumbnailComponent from "~/components/home/ThumbnailComponent.vue";
import WelcomeComponent from "~/components/home/WelcomeComponent.vue";
import SocialMedia from "~/components/home/socialmedia/SocialMedia.vue";
</script>

<template>

  <HeaderComponent></HeaderComponent>
  <ThumbnailComponent></ThumbnailComponent>

  <h1>⚠️DEV RELEASE v1.0.0-BETA⚠️</h1>
  <h2>private Vorschau der laudymedia.de Webseite</h2>

  <WelcomeComponent></WelcomeComponent>
  <SocialMedia></SocialMedia>
  <Footer></Footer>

</template>

<style scoped>

h1 {
  font-size: 4rem;
  color: red;
  text-align: center;
  font-weight: bolder;
}
h2 {
  font-weight: bold;
  color: red;
  text-align: center;
}

</style>