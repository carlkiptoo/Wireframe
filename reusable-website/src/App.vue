<script setup lang="ts">
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import FeatureCards from './components/FeatureCards.vue'

const features = [
  {
    title: 'Feature 1',
    description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
    image: 'https://source.unsplash.com/random/400x200',
  },
  {
    title: 'Feature 2',
    description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
    image: 'https://source.unsplash.com/random/400x200',
  },
  {
    title: 'Feature 3',
    description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.', 
    image: 'https://source.unsplash.com/random/400x200',
  }
]
</script>

<template>
 <NavBar />
 <HeroSection />
 <FeatureCards :features="features" />

</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
