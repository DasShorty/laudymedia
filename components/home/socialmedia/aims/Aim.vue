<script lang="ts">

import axios from "axios";

export default {
  data() {
    return {
      width: "0%",
      currentCount: 0,
      finalCount: 0,
      observer: new IntersectionObserver(this.observerCallback(), {
        root: null, // relative to the viewport
        rootMargin: '0px',
        threshold: 0.3, // trigger when 10% of the div is visible
      })
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
    platform: {
      type: String,
      required: true,
    },
    barColor: {
      type: String,
      required: true
    }
  },
  methods: {

    async requestData() {

      axios.get(`http://localhost:8080/public/aims?platform=${this.platform}`).then(res => {

        this.finalCount = res.data.aimAmount;
        this.currentCount = res.data.currentAmount;

        this.calculateWidth()
        console.log("Width: " + this.width)

        if ((this.currentCount / this.finalCount) * 100 > 100) {
          this.width = "100%";
        }

      })

    },
    calculateWidth() {

      console.log("Current: " + this.currentCount)
      console.log("Max: " + this.finalCount)
      console.log("Percentage: " + this.currentCount / this.finalCount)
      console.log("Percentage: " + this.currentCount / this.finalCount)

      const percentage = (this.currentCount / this.finalCount) * 100;
      this.width = percentage + "%";
    },
    observerCallback(): IntersectionObserverCallback {
      return (entries, observer) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {

            console.log("Animation")

            const progressBar = this.$refs.progressBar as HTMLDivElement;
            progressBar.classList.add("in-view")

            // Stop observing after the first time the element is on screen
            observer.unobserve(progressBar);
          }
        });
      }
    }
  },
  async mounted() {
    // Start observing the target element

    await this.requestData();

    const progressBar = this.$refs.progressBar as HTMLDivElement;
    this.observer.observe(progressBar);
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
    <div class="before-bar" :style="{
      'width': width
    }">
      <div ref="progressBar" class="progress-bar" :style="{
        'width': '100%',
        'background-color': barColor
      }">
      </div>
    </div>

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
  position: relative;
  z-index: 2;
  height: 3.875rem;
  border-radius: 1.938rem;
}

.before-bar {
  position: absolute;
  z-index: 1;
  height: 3.875rem;
  width: 33.875rem;
  border-radius: 1.938rem;
}

.in-view {
  animation: loadBar 2s;
  animation-duration: 2s;
}

@keyframes loadBar {

  0% {
    width: 0;
  }

  100% {
    width: 100%;
  }

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

@media (max-width: 1200px) {
  .bar, .before-bar {
    width: 40rem;
  }
}
@media (max-width: 700px) {
  .bar, .before-bar {
    width: 30rem;
  }
}

@media (max-width: 630px) {
  .bar, .before-bar {
    width: 25rem;
  }
}

@media (max-width: 460px) {
  .bar, .before-bar {
    width: 20rem;
  }
  .amount {
    font-size: 1.7rem;
  }

  .type {
    font-size: 0.8rem;
  }
}


</style>