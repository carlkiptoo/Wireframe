<template>
    <section class="about-section">
        <div class="about-container">
            <div class="about-layout">
                <div class="hexagon-features">
                    <HexagonFeature v-for="(feature, index) in features" :key="index" :title="feature.title"
                        :description="feature.description" :image="feature.image" />
                </div>
                <div class="about-content">
                    <h2 class="about-title">{{ title || "About" }}</h2>
                    <p class="about-description">{{ description || "This is me" }}</p>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
import HexagonFeature from './HexagonFeature.vue'

interface Feature {
    title: string;
    description: string;
    image: string;
}
interface AboutSectionProps {
    title: string;
    description: string;
    features: Feature[];
}
const props = defineProps<AboutSectionProps>();

</script>

<style scoped>
.about-section {
    display: flex;
    justify-content: center;
    padding: 40px 20px;
    background-color: #f8f8f8;
}

.about-container {
    width: 100%;
    max-width: 1200px;
}

.about-content {
    text-align: left;
    flex: 1;
    margin-left: 200px;
}

.about-title {
    font-size: 2em;
    font-weight: bold;
    margin-bottom: 40px;
    color: black;
    text-align: center;
}
.about-layout {
    display: flex;
    justify-content: space-between;
    gap: 40px;
}

.about-description {
    font-size: 0.9em;
    color: #333;
    margin-bottom: 20px;
    line-height: 1.6;
}

.hexagon-features {
    flex: 1;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: repeat(2, 1fr);
    gap: 10px;
    max-width: 400px;
}
</style>