<script setup lang="ts">

defineProps({
  button: {type: Object, required: true}
})

</script>

<template>

  <button><img :src="button.icon" alt="Button Icon"><a :href="button.href">{{ button.name }}</a></button>

</template>

<style scoped>

img {
  height: 1.5rem;
  width: auto;
  margin-right: 0.3rem;
}

button {
  display: flex;
  flex-direction: row;
  align-items: center;
  font-size: 1.3rem;
  padding: 0.3rem 0.5rem;
  border: none;
  border-radius: 0.2rem;
  background-color: var(--purple);
  color: white;
  margin-left: 0.3rem;
  margin-right: 0.3rem;
}

button:hover {
  cursor: pointer;
  transform: scale(1.1);
  transition: 0.2s;
}

a {
  text-decoration: none;
  color: white;
}

</style>