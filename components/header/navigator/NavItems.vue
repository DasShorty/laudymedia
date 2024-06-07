<script setup>
import NavItem from "@/components/header/navigator/NavItem.vue";
</script>

<template>
  <nav>
    <div class="nav-items">
      <NavItem text="Home" link="/"></NavItem>
      <NavItem text="Projekte" link="/projects"></NavItem>
      <NavItem text="Kontakt" link="/contact"></NavItem>
    </div>
  </nav>
</template>

<style scoped>

.nav-items {
  display: flex;
  flex-direction: row;
  text-align: center;
}

nav {
  display: flex;
  flex-direction: row;
}
</style>