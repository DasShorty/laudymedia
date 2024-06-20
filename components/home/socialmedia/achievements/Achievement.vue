<script setup lang="ts">

defineProps({
  text: {
    type: String,
    required: true
  },
  image: {
    type: String,
    required: true
  }
})

</script>

<template>

  <div class="container">
    <img :src="image" alt="Achievement Image">
    <div class="container-text">
      <p>{{ text }}</p>
    </div>
  </div>

</template>

<style scoped>

.container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  background: linear-gradient(90deg, #49315B, #101010);
  margin: 1rem;
  padding: 1rem;
  width: 59.75rem;
  border-radius: 0.625rem;
  transition-duration: 0.3s;
}

.container:hover {
  transform: scale(1.01);
  filter: drop-shadow(0px 1px 3px rgba(40, 40, 40, 0.1));
}

.container img {
  width: 6.25rem;
  height: 6.25rem;
  border-radius: 100%;
  filter: drop-shadow(4px 4px 4px rgba(0, 0, 0, 0.2));
}

.container p {
  font-size: 2rem;
}

.container-text {
  display: flex;
  width: 100%;
  justify-content: center;
}

@media (max-width: 1000px) {
  .container {
    width: 45rem;
  }
  .container img {
    width: 5rem;
    height: 5rem;
  }
}

@media (max-width: 1000px) {
  .container {
    width: 35rem;
  }
  .container img {
    width: 3.5rem;
    height: 3.5rem;
  }
}

@media (max-width: 1000px) {
  .container {
    width: 35rem;
  }
  .container img {
    width: 3.5rem;
    height: 3.5rem;
  }
}
@media (max-width: 650px) {
  .container {
    display: flex;
    flex-direction: column;
    margin: 1rem;
    padding: 1rem;
  }
  .container img {
    width: 3.5rem;
    height: 3.5rem;
  }
}

@media (max-width: 630px) {
  .container {
    width: 30rem;
  }
}

@media (max-width: 630px) {
  .container {
    width: 25rem;
  }
}

@media (max-width: 460px) {
  .container {
    width: 23rem;
  }
}

@media (max-width: 420px) {
  .container {
    width: 22rem;
  }
}




</style>