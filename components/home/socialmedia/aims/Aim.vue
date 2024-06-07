<script lang="ts">


export default {
  data() {
    return {
      width: "20%"
    }
  },
  props: {
    icon: {
      type: String,
      required: true,
    },
    countType: {
      type: String,
      required: true,
    },
    currentCount: {
      type: Number,
      required: true
    },
    finalCount: {
      type: Number,
      required: true
    },
    barColor: {
      type: String,
      required: true
    }
  },
  methods: {
    calculateWidth() {
      const width = (this.currentCount / this.finalCount) * 100;
      return width + "%";
    }
  }
}

</script>

<template>

  <div class="bar">

    <div class="icon">
      <img :src="icon" alt="Aim Icon">
    </div>
    <div class="type">
      <span>{{ countType }}</span>
    </div>
    <div class="amount">
      <p><span id="current-amount">{{ currentCount }}</span> / {{ finalCount }}</p>
    </div>
    <div class="progress-bar" id="progress" :style="{
      'background-color': barColor,
      'width': calculateWidth()
    }"></div>

  </div>

</template>

<style scoped>

#current-amount {
  font-weight: normal;
}

p {
  font-weight: lighter;
}

.bar {
  position: relative;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  height: 3.875rem;
  width: 33.875rem;
  background-color: #222222;
  border-radius: 1.938rem;
  margin: 2rem;
}

.progress-bar {
  position: absolute;
  z-index: 1;
  height: 3.875rem;
  width: 20rem;
  border-radius: 1.938rem;
}

.icon {
  z-index: 2;
  margin-left: 0.4rem;
  display: flex;
  align-items: center;
}

.icon img {
  height: 3.125rem;
  width: 3.125rem;
  border-radius: 100%;
}

.amount {
  margin-right: 0.6rem;
  z-index: 2;
  font-size: 2rem;
}

.type {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 2;
  color: rgba(255, 255, 255, 0.2);
  font-size: 1.25rem;
}

</style>