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
    axios.get("http://localhost:8080/projects").then(value => {
      this.projects = value.data
      console.log(this.projects)
    })
  },
}

</script>

<template>
  <Header></Header>
  <ThumbnailComponent></ThumbnailComponent>

  <main>
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

Footer {
  z-index: -1;
}

</style>