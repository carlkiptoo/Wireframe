<template>
    <section class="feature-cards">
        <div class="card" v-for="(feature, index) in features" :key="index">
            <img :src="feature.image" alt="Feature image" class="feature-image" />
            <h3 class="feature-title">{{ feature.title }}</h3>
            <p class="feature-description">{{ feature.description }}</p>

        </div>
    </section>
</template>

<script setup lang="ts">

import {defineProps} from 'vue'

interface Feature{
    title: string;
    description: string;
    image: string;
}

interface FeatureCardsProps {
    features: Feature[];
}

const props = defineProps<FeatureCardsProps>();


</script>
<style scoped>
.feature-cards {
    display: flex;
    flex-direction: row;
    gap: 20px;
    padding: 40px 20px;
    overflow-x: auto;
}
.card {
    background-color: #fff;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    padding: 20px;
    text-align: center;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    flex-shrink: 0;
    width: 250px;

    
}
.card:hover {
    transform: translateY(-10px);
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}

.feature-image {
    max-width: 100%;
    border-radius: 8px;
    margin-bottom: 20px;
}
.feature-title {
    font-size: 1.5em;
    font-weight: bold;
    margin-bottom: 10px;
}
.feature-description {
    font-size: 1em;
    color: #666;
}


</style>