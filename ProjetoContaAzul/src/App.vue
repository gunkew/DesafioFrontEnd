<script setup>
  import Cards from './components/Cards.vue'
</script>

<template>
<main>
  <header class="top-header">
    <img alt="Desafio Conta Azul Logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
  </header>
  <Cards />
  </main>
</template>

<style>
@import './assets/base.css';

#app {
  font-weight: normal;
}

.top-header {
  display: flex;
  height: 60px;
  background-color: var(--color-header-background);
  overflow: hidden;
  position: fixed;
  width: 100%;
  top: 0;
  z-index: 1;
  text-decoration: none;
  justify-content: center;
  align-items: center;
}

.logo {
  display: block;
  margin: 0 auto 0rem;
  height: 100%;
}

a,
.green {
  text-decoration: none;
  color: hsla(160, 100%, 37%, 1);
  transition: 0.4s;
}

@media (hover: hover) {
  a:hover {
    background-color: hsla(160, 100%, 37%, 0.2);
  }
}

@media (min-width: 601px) {
  body {
    display: flex;
    place-items: center;
  }

  #app {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }

  .logo {
    margin: 0;
  }
}
</style>
