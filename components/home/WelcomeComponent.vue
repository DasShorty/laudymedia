<script setup>

</script>

<template>

  <div class="welcome">

    <img src="../../assets/image/welcome/dave-welcome.jpeg" class="welcome-img" alt="Welcome">
    <hr>
    <div class="welcome-text">
      <h3>Ich bin <span style="color: var(--purple)">Dave</span>!</h3>
      <p>Unter dem Namen “<span style="color: var(--purple)">LaudyTV</span>” produziere ich fast täglich verschiedenen
        Content und kreiere Projekte, um meine Community zu unterhalten.

        Neben meiner Internetpräsenz bin ich gerne in der Natur unterwegs. <span
            style="color: #22F300">Fotografie</span> ist nur eines meiner Hobbys, in der Vergangenheit habe ich meine
        Stimme auch für <span style="color: #82F7FF">Voice-Over</span> genutzt...</p>

      <div class="button">
        <img src="@/assets/image/welcome/web.png" alt="Web">
        <p>Mehr erfahren</p>
      </div>
    </div>

  </div>

</template>

<style scoped>

.welcome img {
  height: 23.688rem;
  width: auto;
  border-radius: 50% 1rem 50% 1rem;
  margin-right: 2.5rem;
}

hr {
  border-radius: 1rem;
  border-color: var(--hr-color);
}

.welcome {
  display: flex;
  flex-direction: row;
  margin-left: 19rem;
  margin-right: 19rem;
  margin-top: 10rem;
  font-size: 1.25rem;
}

h3 {
  font-size: 2.25rem;
}

.welcome-img img {
  margin-right: 2.188rem;
  height: 23.688rem;
  width: auto;
}

.welcome-text {
  margin-left: 2.188rem;
}

.button {
  display: flex;
  flex-direction: row;
  margin-top: 5rem;
  font-size: 1.125rem;
  border-radius: 10px;
  background: linear-gradient(90deg, #49315B 0%, #101010 100%);
  align-items: center;
  justify-content: center;
  padding-left: 0.05rem;
  padding-right: 0.05rem;
  width: 12rem;
  height: 1.875rem;
}

.button:hover {
  transition: 0.2s;
  transform: scale(1.1);
  cursor: pointer;
}

.button img {
  width: 20px;
  height: 20px;
}

</style>