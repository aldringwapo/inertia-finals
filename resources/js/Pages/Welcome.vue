<script setup>
import { Head, Link } from '@inertiajs/vue3';

defineProps({
    canLogin: {
        type: Boolean,
    },
    canRegister: {
        type: Boolean,
    },
    laravelVersion: {
        type: String,
        required: true,
    },
    phpVersion: {
        type: String,
        required: true,
    },
});
</script>

<template>
    <Head title="Welcome" />
    <div class="home">
        <div class="content">
            <div class="auth-links">
                <div class="auth-links-container">
                    <Link :href="route('login')" class="route-link">Log in</Link>
                    <Link v-if="canRegister" :href="route('register')" class="route-link">Register</Link>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
.home {
    background-image: url('https://www.jbmusic.com.ph/__resources/webdata/images/spotlights/1009.png');
    background-repeat: no-repeat;
    background-size: cover;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}

.content {
    text-align: center;
}

.auth-links {
    position: absolute;
    top: 50%;
    left: 20px; /* Adjust the left position as needed */
    transform: translateY(-50%);
}

.auth-links-container {
    display: flex;
    flex-direction: column; /* Change to column to stack buttons vertically */
    align-items: flex-start; /* Align items to the left */
}

.route-link {
    font-weight: 600;
    margin: 10px 0; /* Adjust top and bottom margins */
    padding: 8px 16px;
    border: 2px solid transparent;
    border-radius: 4px;
    transition: all 0.3s ease;
    background-color: orange;
    color: #fff;
    text-decoration: none;
    box-shadow: 0 5px 6px rgba(0, 0, 0, 0.1);
}

.route-link:hover {
    background-color: blue;
    border-color: #4a90e2;
    color: #4a90e2;
}
</style>
