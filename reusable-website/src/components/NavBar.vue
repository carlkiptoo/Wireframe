<template>
   <nav class="navbar">
    <div class="navbar-logo">
        <img :src="logo" alt="Logo" />
    </div>
    <ul class="navbar-links">
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Contact</a></li>
        <li><a href="#">Features</a></li>
    </ul>
    <div class="navbar-actions">
        <button class="cta-button" @click="onActionClick">{{ buttonText }}</button>
    </div>
</nav>
</template>

<script setup lang="ts">
import {defineProps} from 'vue'

interface NavBarProps {
    logo: string;
    buttonText: string;
    onActionClick: () => void;
}

const props = defineProps<NavBarProps>();

</script>

<style scoped>
.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 15px 30px;
    background-color: #333;
    color: white;
}
.navbar-logo img {
    max-height: 50px;
}
.navbar-links {
    list-style: none;
    display: flex;
    gap: 20px;
}
.navbar-links li a {
    text-decoration: none;
    color: white;
    font-weight: bold;
    font-size: 16px;
    transition: color 0.3s;
}

.navbar-links li a:hover {
    color: #007bff;
}
.navbar-actions {
    padding-left: 30px;
    display: flex;
    align-items: center;
}
.navbar-actions .cta-button {
    padding: 10px 20px;
    background-color: #4caf50;
    border: none;
    color: white;
    font-size: 16px;
    cursor: pointer;
    transition: background-color 0.3s;
}
.navbar-actions .cta-button:hover {
    background-color: #007bff;
}
</style>