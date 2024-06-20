<script setup>
</script>

<template>
  <div class="image">
    <h1>LaudyMedia</h1>
    <h2>NEXT GEN CONTENT CREATION</h2>
  </div>
</template>

<style scoped>

.image {
  width: 100%;
  height: auto;
  background-image: url("@/assets/image/webbg.png");
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding-top: 3rem;
  padding-bottom: 3rem;
}

h1 {
  font-family: "ZenDots", sans-serif;
  text-transform: uppercase;
  font-size: 3.125rem;
}

h2 {
  font-family: "ZenDots", sans-serif;
  text-transform: uppercase;
  font-size: 1.875rem;
}

span {
  color: white;
}

img {
  width: 100%;
  height: 100%;
}

@media (max-width: 800px) {
  h1 {
    font-size: 2.125rem;
  }

  h2 {
    font-size: 0.875rem;
  }
}

</style>