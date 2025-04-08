<template>
    <section class="contact-section">
        <div class="contact-container">
            <h2 class="contact-title">Contact Us</h2>
            <p class="contact-description">We're always happy to hear from you. Feel free to reach out to us.</p>

            <form @submit.prevent="onSubmit" class="contact-form">
                <div class="form-group">
                    <label for="name" class="form-label">Full Name</label>
                    <input
                     type="text"
                     id="name"
                     v-model="formData.name"
                     class="form-input"
                     required
                     placeholder="Enter your full name"
                     />
                </div>
                <div class="form-group">
                    <label for="email" class="form-label">Email</label>
                    <input
                     type="email"
                     id="email"
                     v-model="formData.email"
                     class="form-input"
                     required
                     placeholder="Enter your email address"
                     />
                </div>
                <div class="form-group">
                    <label for="message" class="form-label">Message</label>
                    <textarea
                     id="message"
                     v-model="formData.message"
                     class="form-input"
                     required
                     placeholder="Enter your message"
                     ></textarea>
                </div>

                <button type="submit" class="submit-btn">Send Message</button>

            </form>

            <p v-if="formStatus" :class="formStatusClass" class="form-status">
                {{ formStatus }}
            </p>
        </div>
    </section>
</template>

<script setup lang="ts">

import {ref } from 'vue'

interface FormData{
    name: string;
    message: string;
    email: string;
}

const formData = ref<FormData>({
    name: '',
    message: '',
    email: ''
})

const formStatus = ref<string>('');
const formStatusClass = ref<string>('');

const onSubmit = () => {
    if (formData.value.name && formData.value.message && formData.value.email) {
        //Will send the form data to the server later
        setTimeout(() => {
            formStatus.value = 'Message sent successfully!';
            formStatusClass.value = 'success';
            formData.value.name = '';
            formData.value.message = '';
            formData.value.email = '';
            
        }, 1000);
    } else {
        formStatus.value = 'Please fill in all the fields';
        formStatusClass.value = 'error';
    }
}
</script>

<style scoped>
.contact-section {
    background-color: #f4f4f4;
    padding: 60px 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}
.contact-container {
    max-width: 600px;
    width: 100%;
    background-color: #fff;
    padding: 40px;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}
.contact-title {
    font-size: 2em;
    font-weight: bold;
    margin-bottom: 20px;
}
.contact-description {
    font-size: 1rem;
    color: #555;
    margin-bottom: 30px;
}

.contact-form .form-group {
    margin-bottom: 20px;
}

.form-label {
    font-size: 1.1rem;
    margin-bottom: 8px;
    color: #333;
}
.form-input {
    width: 100%;
    padding: 10px;
    border: 1px solid#ccc;
    border-radius: 4px;
    font-size: 1rem;
}
.submit-btn {
    width: 100%;
    padding: 12px;
    background-color: #2c3e50;
    color: white;
    border: none;
    border-radius: 4px;
    font-size: 1.1rem;
    cursor: pointer;
}
.submit-btn:hover {
    background-color: #34496e;
}
.form-status {
    margin-top: 20px;
    font-size: 1rem;
    font-weight: bold;
}
.form-status.success {
    color: #2ecc71;
}
.form-status.error {
    color: #e74c3c;
}



</style>