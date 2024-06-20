<script setup lang="ts">
import NavItem from "@/components/header/navigator/NavItem.vue";
import BurgerMenu from "~/components/header/navigator/BurgerMenu.vue";

let open = false;

function toggleMenu() {

  let elementById = document.getElementById("burger-menu") as HTMLDivElement;

  if (open) {
    open = false;
    elementById.style.display = "none";
  } else {
    open = true;
    elementById.style.display = "block";
  }

}

</script>

<template>
  <nav>
    <div class="nav-items">
      <NavItem text="Home" link="/"></NavItem>
      <NavItem text="Projekte" link="/projekte"></NavItem>
      <NavItem text="Kontakt" link="/kontakt"></NavItem>
    </div>
    <div class="burger-menu"  @click="toggleMenu()">
      <img src="../../../assets/icons/burger-menu.png" alt="menu">
    </div>
    <div id="burger-menu">
      <BurgerMenu></BurgerMenu>
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

.burger-menu {
  display: none;
}

#burger-menu {
  display: none;
  position: absolute;
  right: 0;
  top: 2.3rem;
}

@media (max-width: 650px) {
  .nav-items {
    display: none;
  }

  .burger-menu {
    display: flex;
    align-items: end;
  }
}
</style>