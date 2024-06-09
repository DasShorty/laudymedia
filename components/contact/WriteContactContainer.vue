<script setup lang="ts">

</script>

<template>

  <div class="contact-container">

    <h2>Kontaktformular</h2>

    <p>Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et
      dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita
      kasd gubergren,</p>

    <form>
      <div class="names">
        <input type="text" required placeholder="Vorname*">
        <input type="text" required placeholder="Nachname*">
      </div>
      <input type="email" required placeholder="E-Mail*">
      <input type="text" placeholder="Firma">
      <textarea placeholder="Nachricht*" required rows="10" cols="40"></textarea>
      <div class="form-bottom">
        <span>Pflichtfeld *</span>
        <button type="submit">Senden</button>
      </div>
    </form>

  </div>

</template>

<style scoped>

.contact-container {
  background-color: #222222;
  margin-left: 10rem;
  margin-right: 10rem;
  padding: 2rem;
  width: 35.438rem;
  border-radius: 1rem;
  filter: drop-shadow(4px 4px 4px rgba(0, 0, 0, 0.2));
}

h2 {
  font-size: 1.7rem;
}

p {
  font-size: 1.125rem;
}

textarea {
  resize: none;
}

form {
  display: flex;
  flex-direction: column;
  margin-top: 2rem;
}

input, textarea {
  background-color: #111111;
  padding: 1rem;
  color: white;
  font-size: 1.25rem;
  border: none;
  margin: 0.25rem;
  border-radius: 1rem;
}

input:focus, textarea:focus {
  border: none !important;
  outline: none !important;
}

button {
  border: 1px solid white;
  background-color: #111111 !important;
  border-radius: 0.5rem;
  font-size: 1.25rem;
  color: white;
  padding: 0.5rem 1rem;
  margin: 0.25rem 0.5rem;
}

button:hover {
  cursor: pointer;
}

.form-bottom {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin-top: 0.25rem;
}

.names {
  display: flex;
  flex-direction: row;
  width: 100%;
  justify-content: space-between;
}

.names input {
  width: 15rem;
}

</style>