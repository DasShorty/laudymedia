<script>

export default {
  props: {
    text: {
      type: String,
      required: true
    },
    link: {
      type: String,
      required: true
    }
  }
}
</script>

<template>
  <RouterLink :to="this.link" class="nav-item" :class="{'active': $route.path === this.link}"><p id="nav-text">{{ text }}</p>
  </RouterLink>
</template>

<style scoped>

.nav-item {
  text-decoration: none;
  color: white;
  font-size: 25px;
  margin: 5px 21px;
  transition: 0.3s;
}

.active {
  color: var(--nav-page-title-color);
}

p {
  text-transform: uppercase;
}
</style>