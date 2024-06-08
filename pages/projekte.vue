<script setup lang="ts">

import Header from "~/components/header/Header.vue";
import Footer from "~/components/footer/Footer.vue"
import Project from "~/components/projects/Project.vue";
import ProjectPopup from "~/components/projects/ProjectPopup.vue";
import ThumbnailComponent from "~/components/home/ThumbnailComponent.vue";
import axios from "axios";

const currentProject = {
  "title": "test",
  links: [],
  "description": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.",
  "image": "https://cdn.dasshorty.de/twitch.png",
};

let projects = []

onMounted(() => {

  axios.get("http://localhost:8080/projects/").then(value => {
    projects = value.data
  })

});

const show = false;

</script>

<template>
  <Header></Header>
  <ThumbnailComponent></ThumbnailComponent>

  <main>
    <div class="projects" v-for="project in projects">
      <Project :data="project"></Project>
    </div>

    <ProjectPopup :data="currentProject" :show="show"></ProjectPopup>
  </main>

  <Footer></Footer>
</template>

<style scoped>

main {
  display: flex;
  justify-content: center;
  align-items: center;
}

.projects {
  display: grid;
  gap: 3rem;
  grid-template-columns: auto auto auto;
  margin-top: 5rem;
  margin-left: 10rem;
  margin-right: 10rem;
}

</style>