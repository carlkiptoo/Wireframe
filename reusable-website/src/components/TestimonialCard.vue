<template>
    <div class="testimonial-card">
        <div class="testimonial-avatar">
            <img :src="avatar" class="avatar-image" alt="Testimonial Avatar" />
        </div>
        <div class="testimonial-content">
            <p class="testimonial-text">{{ text || 'Kirui' }}</p>
            <h4 class="testimonial-name">{{ name || 'Kirui' }}</h4>
        </div>
    </div>
</template>

<script setup lang="ts">
import {defineProps} from 'vue'

interface TestimonialCardProps {
    name: string;
    text: string;
    avatar: string;
}

const props = defineProps<TestimonialCardProps>();

</script>

<style scoped>
.testimonial-card {
    display: flex;
    align-items: center;
    background-color: #fff;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    border-radius: 8px;
    padding: 20px;
    max-width: 500px;
    margin: 10px;
}
.testimonial-avatar {
    margin-right: 20px;
}
.avatar-image {
    width: 60px;
    height: 60px;
    border-radius: 50%;
    object-fit: cover;
}
.testimonial-content {
    display: flex;
    flex-direction: column;
}
.testimonial-text {
    font-style: italic;
    color: #555;
    margin-bottom: 10px;
}
.testimonial-name {
    font-weight: bold;
    color: #333;
}
</style>