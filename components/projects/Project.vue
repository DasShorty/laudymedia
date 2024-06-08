<script lang="ts">

export default {
  props: {
    data: {
      type: Object,
      required: true
    }
  }
}
</script>

<template>

  <div class="container">
    <img :src="data.imageRef" alt="Project Image">
    <hr>
    <h3>{{ data.title }}</h3>
    <div v-if="data.description.length < 50">
      <p>{{ data.description.substring(0, 50) + "..." }}</p>
    </div>
    <div v-else>
      <p>{{ data.description }}</p>
    </div>
  </div>

</template>

<style scoped>


.container {
  background-color: rgba(26, 26, 26, 0.8);
  width: 20rem;
  border-radius: 2%;
}

.container:hover {
  cursor: pointer;
}

.container img {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 20rem;
  height: auto;
  border-radius: 2%;
}

hr {
  margin-top: 1rem;
  margin-bottom: 1rem;
  border-color: rgba(145, 70, 255, 0.9);
}

h3 {
  font-size: 2rem;
  color: #8E5BB5;
  background: -webkit-linear-gradient(90deg, #9146FF 10%, #999999 90%);
  font-weight: bold;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  margin-left: 1rem;
}

p {
  margin: 1rem;
}


</style>