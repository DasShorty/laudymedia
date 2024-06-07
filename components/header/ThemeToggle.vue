<script>
export default {
  data() {
    return {
      darkMode: true
    }
  },
  methods: {

    changePosition() {
      if (this.darkMode === true) {
        document.getElementById("toggle").style.animation = "move 1s ease-in-out";
        document.getElementById("toggle").style.paddingLeft = "26px";
      } else {
        document.getElementById("toggle").style.animation = "move 1s ease-in-out alternate";
        document.getElementById("toggle").style.paddingLeft = "4px";
      }
    },
    toggleDarkMode() {
      this.darkMode = !this.darkMode;

      this.changePosition()
    }
  },
  mounted() {
    this.changePosition();
  }
}

</script>

<template>
  <div class="toggle-container">

    <img src="@/assets/image/header/moon.png" alt="Moon">
    <div class="toggle-div" @click="this.toggleDarkMode" id="toggle">
      <div class="toggle-dot"></div>
    </div>
    <img src="@/assets/image/header/sun.png" alt="Sun">

  </div>
</template>

<style scoped>

.toggle-div {
  height: 20px;
  width: 45px;
  background-color: #191C18;
  border-radius: 10px;
  padding-left: 4px;
  display: flex;
  align-items: center;
  transition-duration: 1s;
  animation-duration: 1s;
  margin-left: 5px;
  margin-right: 5px;
}

.toggle-div:hover {
  cursor: pointer;
}

@keyframes move {
  0% {
    padding-left: 4px;
  }

  100% {
    padding-left: 26px;
  }
}

.toggle-dot {
  height: 16px;
  width: 16px;
  background-color: #D9D9D9;
  border-radius: 100px;
}

.toggle-container {
  display: flex;
  flex-direction: row;
  margin-right: 20px;
}

.toggle-container img {
  width: 22px;
  height: auto;
}

</style>