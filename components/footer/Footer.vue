<script setup lang="ts">

const fullYear = new Date().getFullYear();

</script>

<template>

  <footer>

    <div class="text">
      <NuxtLink to="/kontakt">Kontakt</NuxtLink>
      <NuxtLink to="/impressum">Impressum</NuxtLink>
      <NuxtLink to="/datenschutz">Datenschutz</NuxtLink>
      <p>© Copyright {{fullYear}} • LaudyMedia.de</p>
    </div>

  </footer>

</template>

<style scoped>

footer {
  position: relative;
  height: 15.625rem;
  width: 100%;
  background-color: #0C0C0C;
}

a {
  width: 100%;
  color: white;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}

.text {
  display: flex;
  flex-direction: column;
  position: absolute;
  bottom: 4rem;
  left: 4rem;
}

</style>