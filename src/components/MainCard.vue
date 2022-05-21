<template>
  <div class="card">
    <img :src="props.selfieImage" alt="selfie" class="selfie-image" />
    <h1>{{ props.info.handle }}</h1>
    <p>{{ props.info.description }}</p>
    <a :href="`mailto:${props.info.email}`" class="email"
      >Contact: {{ props.info.email }}</a
    >
    <ul class="link-list">
      <li v-for="link in links" :key="link.name">
        <a
          :href="link.href"
          class="links"
          target="_blank"
          rel="noreferrer noopener"
          >{{ link.name }}
          <img
            :src="link.image"
            :alt="link.name"
            class="icon"
            :class="isFacebook(link.name)"
          />
        </a>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
const props = defineProps<{
  selfieImage: string;
  info: any;
  links: any;
}>();

const isFacebook = (link: string) => {
  if (link === 'facebook') {
    return 'facebook';
  }
};
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
  transition: ease-in all 0.2s;
  &:hover {
    background-color: lightskyblue;
    color: black;
  }
}
.email {
  color: white;
  position: relative;
  transition: 0.2s ease-in all;

  &:after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    height: 2px;
    background-color: white;
    width: 0%;
  }

  &:hover {
    width: 100%;
  }
}
.icon {
  width: 1.5rem;
  &.facebook {
    width: 1rem;
  }
}
</style>
