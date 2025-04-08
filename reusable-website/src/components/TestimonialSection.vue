<template>
    <section class="testimonial-section">
        <h2 class="section-title">{{title || 'Testimonials'}}</h2>
        <div class="testimonials-list">
            <TestimonialCard
                v-for="(testimonial, index) in testimonials"
                :key="index"
                :name="testimonial.name"
                :text="testimonial.text"
                :avatar="testimonial.avatar"
                />
        </div>
    </section>
</template>
<script setup lang="ts">
import TestimonialCard from './TestimonialCard.vue'

interface Testimonial{
    name: string;
    text: string;
    avatar: string;
}

interface TestimonialSectionProps {
    title: string;
    testimonials: Testimonial[];
}
const props = defineProps<TestimonialSectionProps>();

</script>

<style scoped>  
.testimonial-section {
    padding: 40px 20px;
    background-color: #f4f4f4;
}
.section-title {
    text-align: center;
    font-size: 2.5em;
    font-weight: bold;
    margin-bottom: 40px;
}
.testimonials-list {
    display: flex;
    flex-direction: row;
    gap: 20px;
    align-items: center;
    max-width: 1200px;
    margin: 0 auto;

}
</style>