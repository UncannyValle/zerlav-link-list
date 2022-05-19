<template>
  <div class="card">
    <img :src="props.selfieImage" alt="selfie" class="selfie-image" />
    <h1>{{ handle }}</h1>
    <ul class="link-list">
      <li v-for="link in links">
        <a :href="link.href" class="links">{{ link.name }}</a>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
const props = defineProps({
  selfieImage: String,
  handle: String,
  links: Object,
});
</script>

<style lang="scss" scoped>
.card {
  border: 3px solid white;
  border-radius: 1rem;
  max-width: 24rem;
  min-width: 18rem;
  width: 100%;
  margin: 0 auto;
  color: white;
  text-align: center;
  gap: 1rem;
}
.selfie-image {
  width: 100%;
  border-radius: 1rem;
}
.link-list {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  padding: 1.5rem;
}
.links {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 3rem;
  border-radius: 0.5rem;
  background-color: #363034;
  color: white;
  padding: 0 1.5rem;
  text-transform: uppercase;
  transition: ease-in all .2s;
  &:hover {
    background-color: lightskyblue;
    color: black;
  }
}
</style>
