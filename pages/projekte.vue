<script lang="ts">

import Header from "~/components/header/Header.vue";
import Footer from "~/components/footer/Footer.vue"
import Project from "~/components/projects/Project.vue";
import ProjectPopup from "~/components/projects/ProjectPopup.vue";
import ThumbnailComponent from "~/components/home/ThumbnailComponent.vue";
import axios from "axios";

export default {
  components: {Footer, Header, ProjectPopup, Project, ThumbnailComponent},
  data() {
    return {
      projects: [],
      currentProject: {},
      show: false
    }
  },
  methods: {
    openPopup(project: Object): void {

      this.currentProject = project;
      this.show = true;
      document.documentElement.style.overflow = 'hidden'

    },
    closePopup(): void {

      this.currentProject = {};
      this.show = false;
      document.documentElement.style.overflow = 'auto'

    }
  },
  mounted() {
    axios.get("http://localhost:8080/public/projects").then(value => {
      this.projects = value.data
    })
  },
}

</script>

<template>
  <Header></Header>
  <ThumbnailComponent></ThumbnailComponent>

  <main>

    <div class="project-title">
      <span>Projects</span>
    </div>

    <div class="projects">
      <Project v-for="project in projects" @click="openPopup(project)" :data="project"></Project>
    </div>

    <ProjectPopup @onPopupClose="closePopup" :data="currentProject" :show="show"></ProjectPopup>
  </main>

  <Footer></Footer>
</template>

<style scoped>

main {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.projects {
  display: grid;
  gap: 3rem;
  grid-template-columns: auto auto auto;
  margin-top: -5rem;
  margin-left: 10rem;
  margin-right: 10rem;
}

Footer {
  z-index: -1;
}

.project-title {
  margin-top: 3rem;
}

.project-title span {
  text-transform: uppercase;
  color: #1A1A1A;
  font-size: 8rem;
  font-family: "ZenDots", sans-serif;
}

@media (max-width: 1200px) {
  .project-title span {
    font-size: 6rem;
  }
  .projects {
    display: grid;
    flex-direction: column;
    gap: 3rem;
    grid-template-columns: auto auto;
    margin-top: -2rem;
    margin-left: 10rem;
    margin-right: 10rem;
  }
}

@media (max-width: 900px) {
  .project-title span {
    font-size: 4rem;
  }
  .projects {
    display: flex;
    flex-direction: column;
    margin-top: 2rem;
  }
}

@media (max-width: 630px) {
  .project-title span {
    font-size: 3rem;
  }

  .projects {
    margin-top: 2rem;
  }
}

</style>