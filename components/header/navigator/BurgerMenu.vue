<script setup lang="ts">

import NavItem from "~/components/header/navigator/NavItem.vue";
import ThemeToggle from "../ThemeToggle.vue";
</script>

<template>

  <div class="container">


    <NavItem text="Home" link="/"></NavItem>
    <NavItem text="Projekte" link="/projekte"></NavItem>
    <NavItem text="Kontakt" link="/kontakt"></NavItem>
    <div class="toggle">
      <ThemeToggle></ThemeToggle>
    </div>

  </div>

</template>

<style scoped>

.container {
  background-color: #0F0F11;
  padding-left: 1rem;
  padding-right: 1rem;
  border-bottom-left-radius: 0.4rem;
  transition: 1s;
  animation: slideIn 1s ease-out forwards;
}

.toggle {
  padding-bottom: 1rem;
}

@keyframes slideIn {
  0% {
    transform: translateX(100%);
    opacity: 0;
  }
  100% {
    transform: translateX(0);
    opacity: 1;
  }
}

</style>