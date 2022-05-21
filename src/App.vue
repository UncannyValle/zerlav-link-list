<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import MainCard from './components/MainCard.vue';
import selfieImage from './assets/images/image01.jpg';
import lenaLinks from './lena-links.json';

const links = lenaLinks.links;
const info = lenaLinks;
</script>

<template>
  <main>
    <MainCard :selfieImage="selfieImage" :info="info" :links="links" />
  </main>
</template>

<style lang="scss">
main {
  // background-color: var(--primary);
  min-height: 100vh;
  padding: 2rem;
  @media (max-width: 512px) {
    padding: 1rem;
  }
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
