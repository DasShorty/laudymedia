<script setup lang="ts">

import ProjectPopupButton from "~/components/projects/ProjectPopupButton.vue";

defineProps({

  data: {type: Object, required: true},
  show: {type: Boolean, default: false},

});

</script>

<template>

  <div class="popup" v-if="show">
    <div class="center">
      <div class="content">

        <div class="title">
          <h1>{{ data.title }}</h1>
        </div>
        <div class="close-button" @click="$emit('onPopupClose')">
          <img src="/assets/icons/close.png" alt="Close Button">
        </div>
        <div class="image-text">
          <div class="image">
            <img :src="data.imageRef" alt="Project Image">
          </div>
          <div class="text">
            <p>{{ data.description }}</p>
          </div>
        </div>
        <div class="buttons">
          <ProjectPopupButton v-for='button in data.links' :button='button'></ProjectPopupButton>
        </div>
      </div>
    </div>
  </div>

</template>

<style scoped>
.popup {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 100%;
  height: 100%;
  background-color: rgba(10, 10, 10, 0.50);
}

.center {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: #1A1A1A;
  width: 80%;
  height: 80%;
}

.content {
  position: relative;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 3rem;
}

.image-text {
  display: flex;
  flex-direction: row;
  width: 100%;
  height: 100%;
  justify-content: space-evenly;
  align-items: center;
}

.image img {

  width: 20rem;
  height: auto;
  border-radius: 0.625rem;
  filter: drop-shadow(4px 4px 4px rgba(0, 0, 0, 0.2));

}

.title {
  text-align: center;
  font-weight: bold;
  font-size: 1.5rem;
}

.text  {
  padding: 2rem;
  font-size: 1.2rem;
}

.buttons {
  margin-top: 3rem;
  display: flex;
}

.close-button {
  position: fixed;
  right: 1rem;
  top: 1rem;
  cursor: pointer;
}

</style>