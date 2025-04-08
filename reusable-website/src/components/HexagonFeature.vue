<template>
    <div class="hexagon-container">
        <div class="hexagon">
            <div class="hexagon-content">
                <img :src="image" alt="Feature Image" class="hexagon-image" />
                <h4 class="hexagon-title">{{ title || "Hello" }}</h4>
                <p class="hexagon-description">{{ description || "About me" }}</p>
            </div>

        </div>
    </div>
</template>

<script setup lang="ts">
import {defineProps} from 'vue'

interface HexagonFeatureProps {
    title: string;
    description: string;
    image: string;
}

const props = defineProps<HexagonFeatureProps>();
</script>

<style scoped>  
.hexagon-container {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 20px;
}
.hexagon {
    width: 200px;
    height: 230px;
    background-color: #fff;
    clip-path: polygon(50% 0%, 100% 25%, 100% 75%, 50% 100%, 0% 75%, 0% 25%);
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    text-align: center;
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: center;
}
.hexagon-image {
    max-width: 100%;
    height: auto;
    border-radius: 50%;
    margin-bottom: 15px;
}
.hexagon-title {
    font-size: 1.2em;
    font-weight: bold;
    margin-bottom: 10px;
    color: #666;

}
.hexagon-description {
    font-size: 0.9em;
    color: #666;
}
</style>