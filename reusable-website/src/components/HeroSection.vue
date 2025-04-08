<template>
    <section class="hero">
        <div class="hero-content">
            <h1>{{ title }}</h1>
            <p>{{ subtitle }}</p>
            <button class="cta-button" @click="onButtonClick">{{ buttonText }}</button>
        </div>
        <div class="hero-image">
            <img :src="imageSrc" alt="Hero Image" />
        </div>
    </section>
</template>

<script setup lang="ts">
import {defineProps} from 'vue'

interface HeroSectionProps {
    title: string;
    subtitle: string;
    buttonText: string;
    imageSrc: string; 
    onButtonClick: () => void;
}

const props = defineProps<HeroSectionProps>();

</script>

<style scoped>
.hero {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 50px 20px;
    background-color: #f4f4f4;
}
.hero-content {
    max-width: 50%;
}
.hero-content h1 {
    font-size: 3em;
    font-weight: bold;
    margin-bottom: 20px;
    color: black;

}
.hero-content p {
    font-size: 1.5em;
    margin-bottom: 30px;
    color: black;
}
.hero-content .cta-button {
    padding: 12px 25px;
    font-size: 18px;
    background-color: #4caf50;
    color: white;
    border: none;
    cursor: pointer;
    transition: background-color 0.3s;
}
.hero-content .cta-button:hover {
    background-color: #007bff;
}
.hero-image img{
    max-width: 100%;
    height: auto;
    border-radius: 10px;
}

</style>