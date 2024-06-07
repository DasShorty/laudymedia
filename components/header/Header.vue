<script setup>

import ThemeToggle from "@/components/header/ThemeToggle.vue";
import NavItems from "@/components/header/navigator/NavItems.vue";
</script>

<template>
  <header>
    <div class="nav-container">
      <NavItems></NavItems>
    </div>
    <ThemeToggle></ThemeToggle>
  </header>
</template>

<style scoped>
header {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  background: #0F0F11;
  padding: 0 16px;
}

.nav-container {
  flex-grow: 10;
  display: flex;
  justify-content: center;
  padding-left: 99px;
}
</style>