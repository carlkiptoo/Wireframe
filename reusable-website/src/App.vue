<script setup lang="ts">
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import FeatureCards from './components/FeatureCards.vue'
import AboutSection from './components/AboutSection.vue'
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

const aboutSectionData = {
  title: 'About Gentle Dental Care',
  description: 'We provide the best dental care to our patients. Our team of dentists is highly skilled and dedicated to providing the best dental care possible. We are committed to providing excellent dental care and ensuring that our patients receive the best possible care.',
  features: [
    {
      title: 'Teeth Cleaning',
      description: 'Our teeth cleaning services are highly effective and provide a thorough cleaning of your teeth. We use only the best cleaning products to ensure that your teeth are clean and healthy.',
      image: 'https://source.unsplash.com/random/400x200',
    },
    {
      title: 'Oral Care',
      description: 'Our oral care services are designed to provide the best possible oral care to your teeth. We use only the best dental products to ensure that your teeth are healthy and strong.',
      image: 'https://source.unsplash.com/random/400x200',
    },
    {
      title: 'Dental Exams',
      description: 'Our dental exams are conducted by experienced dentists who are highly skilled and knowledgeable. We use only the best dental equipment to ensure that your teeth are healthy and strong.',
      image: 'https://source.unsplash.com/random/400x200',
    },
    {
      title: 'Dental Insurance',
      description: 'We offer comprehensive dental insurance to our patients. Our dental insurance covers all of your dental expenses, including cleanings, fillings, and dental exams.',
      image: 'https://source.unsplash.com/random/400x200',
    }
  ]
}
</script>

<template>
 <NavBar />
 <HeroSection />
 <FeatureCards :features="features" />
 <AboutSection
 :title="aboutSectionData.title"
 :description="aboutSectionData.description"
 :features="aboutSectionData.features"
 
 />
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
