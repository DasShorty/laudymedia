<script setup>
import ThemeToggle from "@/components/header/ThemeToggle.vue";
import NavItems from "@/components/header/navigator/NavItems.vue";
</script>

<template>
  <header>
    <div class="nav-container">
      <NavItems></NavItems>
    </div>
    <div class="theme-toggle">
      <ThemeToggle></ThemeToggle>
    </div>
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

@media (max-width: 650px) {
  .theme-toggle {
    display: none;
  }

  .nav-container {
    flex-grow: 10;
    display: flex;
    justify-content: end;
    margin-top: 1rem;
    margin-bottom: 1rem;
  }
}
</style>