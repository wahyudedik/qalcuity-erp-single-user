<script setup lang="ts">
import { Head, Link } from '@inertiajs/vue3';
</script>

<style>
/* Custom styles can be added here */
html {
    scroll-behavior: smooth;
}

.hero-section {
    background-image: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)), url('/images/concrete-hero.jpg');
    background-size: cover;
    background-position: center;
}

@media (prefers-color-scheme: dark) {
    .hero-section {
        background-image: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('/images/concrete-hero.jpg');
    }
}
</style>

<template>

    <Head title="Qalcuity Concrete - Premium Liquid Concrete Solutions">
        <link rel="preconnect" href="https://rsms.me/" />
        <link rel="stylesheet" href="https://rsms.me/inter/inter.css" />
    </Head>
    <div class="flex min-h-screen flex-col bg-gray-50 text-gray-800 dark:bg-gray-900 dark:text-gray-100">
        <!-- Navigation Bar -->
        <header class="bg-white shadow-sm dark:bg-gray-800">
            <div class="container mx-auto flex items-center justify-between p-4">
                <div class="flex items-center space-x-2">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-blue-600 dark:text-blue-400"
                        viewBox="0 0 20 20" fill="currentColor">
                        <path fill-rule="evenodd"
                            d="M9.504 1.132a1 1 0 01.992 0l1.75 1a1 1 0 11-.992 1.736L10 3.152l-1.254.716a1 1 0 11-.992-1.736l1.75-1zM5.618 4.504a1 1 0 01-.372 1.364L5.016 6l.23.132a1 1 0 11-.992 1.736L4 7.723V8a1 1 0 01-2 0V6a.996.996 0 01.52-.878l1.734-.99a1 1 0 011.364.372zm8.764 0a1 1 0 011.364-.372l1.733.99A1.002 1.002 0 0118 6v2a1 1 0 11-2 0v-.277l-.254.145a1 1 0 11-.992-1.736l.23-.132-.23-.132a1 1 0 01-.372-1.364zm-7 4a1 1 0 011.364-.372L10 8.848l1.254-.716a1 1 0 11.992 1.736L11 10.58V12a1 1 0 11-2 0v-1.42l-1.246-.712a1 1 0 01-.372-1.364zM3 11a1 1 0 011 1v1.42l1.246.712a1 1 0 11-.992 1.736l-1.75-1A1 1 0 012 14v-2a1 1 0 011-1zm14 0a1 1 0 011 1v2a1 1 0 01-.504.868l-1.75 1a1 1 0 11-.992-1.736L16 13.42V12a1 1 0 011-1zm-9.618 5.504a1 1 0 011.364-.372l.254.145V16a1 1 0 112 0v.277l.254-.145a1 1 0 11.992 1.736l-1.735.992a.995.995 0 01-1.022 0l-1.735-.992a1 1 0 01-.372-1.364z"
                            clip-rule="evenodd" />
                    </svg>
                    <span class="text-xl font-bold">Qalcuity Concrete</span>
                </div>
                <nav class="hidden md:flex space-x-6">
                    <a href="#home" class="font-medium hover:text-blue-600 dark:hover:text-blue-400">Home</a>
                    <a href="#products" class="font-medium hover:text-blue-600 dark:hover:text-blue-400">Products</a>
                    <a href="#services" class="font-medium hover:text-blue-600 dark:hover:text-blue-400">Services</a>
                    <a href="#about" class="font-medium hover:text-blue-600 dark:hover:text-blue-400">About Us</a>
                    <a href="#contact" class="font-medium hover:text-blue-600 dark:hover:text-blue-400">Contact</a>
                </nav>
                <div class="flex items-center space-x-4">
                    <Link v-if="$page.props.auth.user" :href="route('dashboard')"
                        class="rounded-md bg-blue-600 px-4 py-2 text-sm font-medium text-white hover:bg-blue-700 dark:bg-blue-500 dark:hover:bg-blue-600">
                    Dashboard
                    </Link>
                    <template v-else>
                        <Link :href="route('login')"
                            class="rounded-md px-4 py-2 text-sm font-medium hover:bg-gray-100 dark:hover:bg-gray-700">
                        Log in
                        </Link>
                        <Link :href="route('register')"
                            class="rounded-md bg-blue-600 px-4 py-2 text-sm font-medium text-white hover:bg-blue-700 dark:bg-blue-500 dark:hover:bg-blue-600">
                        Register
                        </Link>
                    </template>
                </div>
            </div>
        </header>

        <!-- Hero Section -->
        <section id="home" class="relative bg-gradient-to-r from-blue-600 to-blue-800 py-20 text-white">
            <div class="container mx-auto px-4">
                <div class="grid grid-cols-1 gap-12 md:grid-cols-2">
                    <div class="flex flex-col justify-center">
                        <h1 class="mb-6 text-4xl font-bold leading-tight md:text-5xl lg:text-6xl">Premium Liquid
                            Concrete Solutions</h1>
                        <p class="mb-8 text-lg text-blue-100">Providing high-quality concrete products for construction
                            projects of all sizes. Reliable, durable, and delivered on time.</p>
                        <div class="flex flex-col space-y-4 sm:flex-row sm:space-x-4 sm:space-y-0">
                            <a href="#products"
                                class="rounded-md bg-white px-6 py-3 text-center font-semibold text-blue-600 shadow-md hover:bg-gray-100">Our
                                Products</a>
                            <a href="#contact"
                                class="rounded-md border border-white px-6 py-3 text-center font-semibold hover:bg-white hover:text-blue-600">Contact
                                Us</a>
                        </div>
                    </div>
                    <div class="hidden md:flex items-center justify-center">
                        <img src="/images/concrete-mixer.svg" alt="Concrete Mixer" class="max-h-80 w-auto" />
                    </div>
                </div>
            </div>
            <div class="absolute bottom-0 left-0 right-0">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
                    <path fill="#f9fafb" fill-opacity="1"
                        d="M0,96L48,112C96,128,192,160,288,160C384,160,480,128,576,122.7C672,117,768,139,864,149.3C960,160,1056,160,1152,138.7C1248,117,1344,75,1392,53.3L1440,32L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z">
                    </path>
                </svg>
            </div>
        </section>

        <!-- Features Section -->
        <section class="py-16">
            <div class="container mx-auto px-4">
                <div class="mb-12 text-center">
                    <h2 class="mb-4 text-3xl font-bold">Why Choose Qalcuity Concrete?</h2>
                    <p class="mx-auto max-w-2xl text-gray-600 dark:text-gray-400">We combine innovative technology with
                        years of industry experience to deliver the best concrete solutions for your projects.</p>
                </div>
                <div class="grid grid-cols-1 gap-8 sm:grid-cols-2 lg:grid-cols-4">
                    <div class="rounded-lg bg-white p-6 shadow-md dark:bg-gray-800">
                        <div class="mb-4 rounded-full bg-blue-100 p-3 inline-block dark:bg-blue-900">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-blue-600 dark:text-blue-400"
                                fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z" />
                            </svg>
                        </div>
                        <h3 class="mb-2 text-xl font-semibold">Premium Quality</h3>
                        <p class="text-gray-600 dark:text-gray-400">Our concrete meets the highest industry standards
                            for strength and durability.</p>
                    </div>
                    <div class="rounded-lg bg-white p-6 shadow-md dark:bg-gray-800">
                        <div class="mb-4 rounded-full bg-blue-100 p-3 inline-block dark:bg-blue-900">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-blue-600 dark:text-blue-400"
                                fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
                            </svg>
                        </div>
                        <h3 class="mb-2 text-xl font-semibold">On-Time Delivery</h3>
                        <p class="text-gray-600 dark:text-gray-400">We understand that time is critical in construction
                            projects and deliver when promised.</p>
                    </div>
                    <div class="rounded-lg bg-white p-6 shadow-md dark:bg-gray-800">
                        <div class="mb-4 rounded-full bg-blue-100 p-3 inline-block dark:bg-blue-900">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-blue-600 dark:text-blue-400"
                                fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M13 10V3L4 14h7v7l9-11h-7z" />
                            </svg>
                        </div>
                        <h3 class="mb-2 text-xl font-semibold">Custom Solutions</h3>
                        <p class="text-gray-600 dark:text-gray-400">We offer tailored concrete mixes to meet your
                            specific project requirements.</p>
                    </div>
                    <div class="rounded-lg bg-white p-6 shadow-md dark:bg-gray-800">
                        <div class="mb-4 rounded-full bg-blue-100 p-3 inline-block dark:bg-blue-900">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-blue-600 dark:text-blue-400"
                                fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z" />
                            </svg>
                        </div>
                        <h3 class="mb-2 text-xl font-semibold">Expert Support</h3>
                        <p class="text-gray-600 dark:text-gray-400">Our team of concrete specialists is always available
                            to provide technical assistance.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Products Section -->
        <section id="products" class="bg-gray-100 py-16 dark:bg-gray-800">
            <div class="container mx-auto px-4">
                <div class="mb-12 text-center">
                    <h2 class="mb-4 text-3xl font-bold">Our Concrete Products</h2>
                    <p class="mx-auto max-w-2xl text-gray-600 dark:text-gray-400">We offer a wide range of high-quality
                        concrete products to meet various construction needs.</p>
                </div>
                <div class="grid grid-cols-1 gap-8 md:grid-cols-2 lg:grid-cols-3">
                    <div
                        class="overflow-hidden rounded-lg bg-white shadow-md transition-transform hover:scale-105 dark:bg-gray-700">
                        <img src="/images/ready-mix.jpg" alt="Ready Mix Concrete" class="h-48 w-full object-cover" />
                        <div class="p-6">
                            <h3 class="mb-2 text-xl font-semibold">Ready Mix Concrete</h3>
                            <p class="mb-4 text-gray-600 dark:text-gray-400">Our ready-mix concrete is professionally
                                prepared and delivered to your site, ready to pour.</p>
                            <div class="flex justify-between">
                                <span class="text-blue-600 dark:text-blue-400">Starting at $85/m³</span>
                                <a href="#contact" class="text-blue-600 hover:underline dark:text-blue-400">Request
                                    Quote</a>
                            </div>
                        </div>
                    </div>
                    <div
                        class="overflow-hidden rounded-lg bg-white shadow-md transition-transform hover:scale-105 dark:bg-gray-700">
                        <img src="/images/high-strength.jpg" alt="High Strength Concrete"
                            class="h-48 w-full object-cover" />
                        <div class="p-6">
                            <h3 class="mb-2 text-xl font-semibold">High Strength Concrete</h3>
                            <p class="mb-4 text-gray-600 dark:text-gray-400">Specially formulated for projects requiring
                                superior strength and durability under heavy loads.</p>
                            <div class="flex justify-between">
                                <span class="text-blue-600 dark:text-blue-400">Starting at $110/m³</span>
                                <a href="#contact" class="text-blue-600 hover:underline dark:text-blue-400">Request
                                    Quote</a>
                            </div>
                        </div>
                    </div>
                    <div
                        class="overflow-hidden rounded-lg bg-white shadow-md transition-transform hover:scale-105 dark:bg-gray-700">
                        <img src="/images/decorative.jpg" alt="Decorative Concrete" class="h-48 w-full object-cover" />
                        <div class="p-6">
                            <h3 class="mb-2 text-xl font-semibold">Decorative Concrete</h3>
                            <p class="mb-4 text-gray-600 dark:text-gray-400">Enhance the aesthetic appeal of your
                                project with our decorative concrete options.</p>
                            <div class="flex justify-between">
                                <span class="text-blue-600 dark:text-blue-400">Starting at $125/m³</span>
                                <a href="#contact" class="text-blue-600 hover:underline dark:text-blue-400">Request
                                    Quote</a>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="mt-12 text-center">
                    <a href="#contact"
                        class="rounded-md bg-blue-600 px-6 py-3 font-semibold text-white hover:bg-blue-700 dark:bg-blue-500 dark:hover:bg-blue-600">View
                        All Products</a>
                </div>
            </div>
        </section>

        <!-- Services Section -->
        <section id="services" class="py-16">
            <div class="container mx-auto px-4">
                <div class="mb-12 text-center">
                    <h2 class="mb-4 text-3xl font-bold">Our Services</h2>
                    <p class="mx-auto max-w-2xl text-gray-600 dark:text-gray-400">Beyond providing quality concrete, we
                        offer comprehensive services to ensure your project's success.</p>
                </div>
                <div class="grid grid-cols-1 gap-8 md:grid-cols-2">
                    <div class="flex flex-col rounded-lg bg-white p-6 shadow-md dark:bg-gray-800">
                        <div
                            class="mb-4 flex h-12 w-12 items-center justify-center rounded-full bg-blue-100 dark:bg-blue-900">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-blue-600 dark:text-blue-400"
                                fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M19 21V5a2 2 0 00-2-2H7a2 2 0 00-2 2v16m14 0h2m-2 0h-5m-9 0H3m2 0h5M9 7h1m-1 4h1m4-4h1m-1 4h1m-5 10v-5a1 1 0 011-1h2a1 1 0 011 1v5m-4 0h4" />
                            </svg>
                        </div>
                        <h3 class="mb-2 text-xl font-semibold">Concrete Delivery</h3>
                        <p class="mb-4 text-gray-600 dark:text-gray-400">We deliver concrete directly to your
                            construction site with our fleet of mixer trucks, ensuring it arrives fresh and ready to
                            use.</p>
                        <ul class="mb-4 space-y-2 text-gray-600 dark:text-gray-400">
                            <li class="flex items-center">
                                <svg xmlns="http://www.w3.org/2000/svg" class="mr-2 h-5 w-5 text-green-500" fill="none"
                                    viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                        d="M5 13l4 4L19 7" />
                                </svg>
                                Scheduled deliveries
                            </li>
                            <li class="flex items-center">
                                <svg xmlns="http://www.w3.org/2000/svg" class="mr-2 h-5 w-5 text-green-500" fill="none"
                                    viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                        d="M5 13l4 4L19 7" />
                                </svg>
                                GPS-tracked vehicles
                            </li>
                            <li class="flex items-center">
                                <svg xmlns="http://www.w3.org/2000/svg" class="mr-2 h-5 w-5 text-green-500" fill="none"
                                    viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                        d="M5 13l4 4L19 7" />
                                </svg>
                                Temperature-controlled transport
                            </li>
                        </ul>
                    </div>
                    <div class="flex flex-col rounded-lg bg-white p-6 shadow-md dark:bg-gray-800">
                        <div
                            class="mb-4 flex h-12 w-12 items-center justify-center rounded-full bg-blue-100 dark:bg-blue-900">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-blue-600 dark:text-blue-400"
                                fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M9 3v2m6-2v2M9 19v2m6-2v2M5 9H3m2 6H3m18-6h-2m2 6h-2M7 19h10a2 2 0 002-2V7a2 2 0 00-2-2H7a2 2 0 00-2 2v10a2 2 0 002 2zM9 9h6v6H9V9z" />
                            </svg>
                        </div>
                        <h3 class="mb-2 text-xl font-semibold">Concrete Pumping</h3>
                        <p class="mb-4 text-gray-600 dark:text-gray-400">Our concrete pumping service allows for
                            efficient placement of concrete in hard-to-reach areas or at heights where direct pouring
                            isn't possible.</p>
                        <ul class="mb-4 space-y-2 text-gray-600 dark:text-gray-400">
                            <li class="flex items-center">
                                <svg xmlns="http://www.w3.org/2000/svg" class="mr-2 h-5 w-5 text-green-500" fill="none"
                                    viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                        d="M5 13l4 4L19 7" />
                                </svg>
                                Boom pumps for high-rise projects
                            </li>
                            <li class="flex items-center">
                                <svg xmlns="http://www.w3.org/2000/svg" class="mr-2 h-5 w-5 text-green-500" fill="none"
                                    viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                        d="M5 13l4 4L19 7" />
                                </svg>
                                Line pumps for underground work
                            </li>
                            <li class="flex items-center">
                                <svg xmlns="http://www.w3.org/2000/svg" class="mr-2 h-5 w-5 text-green-500" fill="none"
                                    viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                        d="M5 13l4 4L19 7" />
                                </svg>
                                Experienced pump operators
                            </li>
                        </ul>
                    </div>
                    <div class="flex flex-col rounded-lg bg-white p-6 shadow-md dark:bg-gray-800">
                        <div
                            class="mb-4 flex h-12 w-12 items-center justify-center rounded-full bg-blue-100 dark:bg-blue-900">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-blue-600 dark:text-blue-400"
                                fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M11 5H6a2 2 0 00-2 2v11a2 2 0 002 2h11a2 2 0 002-2v-5m-1.414-9.414a2 2 0 112.828 2.828L11.828 15H9v-2.828l8.586-8.586z" />
                            </svg>
                        </div>
                        <h3 class="mb-2 text-xl font-semibold">Mix Design Consultation</h3>
                        <p class="mb-4 text-gray-600 dark:text-gray-400">Our engineers work with you to develop the
                            perfect concrete mix for your specific project requirements and environmental conditions.
                        </p>
                        <ul class="mb-4 space-y-2 text-gray-600 dark:text-gray-400">
                            <li class="flex items-center">
                                <svg xmlns="http://www.w3.org/2000/svg" class="mr-2 h-5 w-5 text-green-500" fill="none"
                                    viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                        d="M5 13l4 4L19 7" />
                                </svg>
                                Custom strength specifications
                            </li>
                            <li class="flex items-center">
                                <svg xmlns="http://www.w3.org/2000/svg" class="mr-2 h-5 w-5 text-green-500" fill="none"
                                    viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                        d="M5 13l4 4L19 7" />
                                </svg>
                                Special admixtures for performance
                            </li>
                            <li class="flex items-center">
                                <svg xmlns="http://www.w3.org/2000/svg" class="mr-2 h-5 w-5 text-green-500" fill="none"
                                    viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                        d="M5 13l4 4L19 7" />
                                </svg>
                                Environmental adaptation
                            </li>
                        </ul>
                    </div>
                    <div class="flex flex-col rounded-lg bg-white p-6 shadow-md dark:bg-gray-800">
                        <div
                            class="mb-4 flex h-12 w-12 items-center justify-center rounded-full bg-blue-100 dark:bg-blue-900">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-blue-600 dark:text-blue-400"
                                fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M9 12l2 2 4-4M7.835 4.697a3.42 3.42 0 001.946-.806 3.42 3.42 0 014.438 0 3.42 3.42 0 001.946.806 3.42 3.42 0 013.138 3.138 3.42 3.42 0 00.806 1.946 3.42 3.42 0 010 4.438 3.42 3.42 0 00-.806 1.946 3.42 3.42 0 01-3.138 3.138 3.42 3.42 0 00-1.946.806 3.42 3.42 0 01-4.438 0 3.42 3.42 0 00-1.946-.806 3.42 3.42 0 01-3.138-3.138 3.42 3.42 0 00-.806-1.946 3.42 3.42 0 010-4.438 3.42 3.42 0 00.806-1.946 3.42 3.42 0 013.138-3.138z" />
                            </svg>
                        </div>
                        <h3 class="mb-2 text-xl font-semibold">Quality Testing</h3>
                        <p class="mb-4 text-gray-600 dark:text-gray-400">We provide comprehensive testing services to
                            ensure your concrete meets all required specifications and quality standards.</p>
                        <ul class="mb-4 space-y-2 text-gray-600 dark:text-gray-400">
                            <li class="flex items-center">
                                <svg xmlns="http://www.w3.org/2000/svg" class="mr-2 h-5 w-5 text-green-500" fill="none"
                                    viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                        d="M5 13l4 4L19 7" />
                                </svg>
                                Slump testing
                            </li>
                            <li class="flex items-center">
                                <svg xmlns="http://www.w3.org/2000/svg" class="mr-2 h-5 w-5 text-green-500" fill="none"
                                    viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                        d="M5 13l4 4L19 7" />
                                </svg>
                                Compression strength testing
                            </li>
                            <li class="flex items-center">
                                <svg xmlns="http://www.w3.org/2000/svg" class="mr-2 h-5 w-5 text-green-500" fill="none"
                                    viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                        d="M5 13l4 4L19 7" />
                                </svg>
                                Certified lab reports
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <!-- About Section -->
        <section id="about" class="bg-gray-100 py-16 dark:bg-gray-800">
            <div class="container mx-auto px-4">
                <div class="grid grid-cols-1 gap-12 md:grid-cols-2">
                    <div>
                        <h2 class="mb-6 text-3xl font-bold">About Qalcuity Concrete</h2>
                        <p class="mb-4 text-gray-600 dark:text-gray-400">
                            Founded in 2005, Qalcuity Concrete has grown to become a leading provider of high-quality
                            concrete solutions in the region. With state-of-the-art production facilities and a fleet of
                            modern delivery vehicles, we serve contractors, builders, and developers on projects of all
                            sizes.
                        </p>
                        <p class="mb-4 text-gray-600 dark:text-gray-400">
                            Our commitment to quality, reliability, and customer satisfaction has earned us a reputation
                            as the preferred concrete supplier for critical infrastructure projects, commercial
                            developments, and residential construction.
                        </p>
                        <p class="mb-6 text-gray-600 dark:text-gray-400">
                            At Qalcuity Concrete, we continuously invest in research and development to improve our
                            products and reduce our environmental footprint through sustainable practices and materials.
                        </p>
                        <div class="flex flex-wrap gap-4">
                            <div class="flex items-center">
                                <span class="mr-2 text-3xl font-bold text-blue-600 dark:text-blue-400">15+</span>
                                <span class="text-gray-600 dark:text-gray-400">Years of Experience</span>
                            </div>
                            <div class="flex items-center">
                                <span class="mr-2 text-3xl font-bold text-blue-600 dark:text-blue-400">500+</span>
                                <span class="text-gray-600 dark:text-gray-400">Projects Completed</span>
                            </div>
                            <div class="flex items-center">
                                <span class="mr-2 text-3xl font-bold text-blue-600 dark:text-blue-400">98%</span>
                                <span class="text-gray-600 dark:text-gray-400">Client Satisfaction</span>
                            </div>
                        </div>
                    </div>
                    <div class="grid grid-cols-2 gap-4">
                        <img src="/images/factory-1.jpg" alt="Concrete Factory" class="rounded-lg shadow-md" />
                        <img src="/images/mixer-truck.jpg" alt="Mixer Truck" class="rounded-lg shadow-md" />
                        <img src="/images/pouring.jpg" alt="Concrete Pouring" class="rounded-lg shadow-md" />
                        <img src="/images/testing.jpg" alt="Quality Testing" class="rounded-lg shadow-md" />
                    </div>
                </div>
            </div>
        </section>

        <!-- Testimonials Section -->
        <section class="py-16">
            <div class="container mx-auto px-4">
                <div class="mb-12 text-center">
                    <h2 class="mb-4 text-3xl font-bold">What Our Clients Say</h2>
                    <p class="mx-auto max-w-2xl text-gray-600 dark:text-gray-400">Don't just take our word for it.
                        Here's what our satisfied customers have to say about our concrete products and services.</p>
                </div>
                <div class="grid grid-cols-1 gap-8 md:grid-cols-2 lg:grid-cols-3">
                    <div class="rounded-lg bg-white p-6 shadow-md dark:bg-gray-800">
                        <div class="mb-4 flex">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-yellow-400" viewBox="0 0 20 20"
                                fill="currentColor">
                                <path
                                    d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                            </svg>
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-yellow-400" viewBox="0 0 20 20"
                                fill="currentColor">
                                <path
                                    d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                            </svg>
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-yellow-400" viewBox="0 0 20 20"
                                fill="currentColor">
                                <path
                                    d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                            </svg>
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-yellow-400" viewBox="0 0 20 20"
                                fill="currentColor">
                                <path
                                    d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                            </svg>
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-yellow-400" viewBox="0 0 20 20"
                                fill="currentColor">
                                <path
                                    d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                            </svg>
                        </div>
                        <p class="mb-4 italic text-gray-600 dark:text-gray-400">"Qalcuity Concrete has been our go-to
                            supplier for all our major construction projects. Their consistent quality and on-time
                            delivery have been crucial to our success."</p>
                        <div class="flex items-center">
                            <img src="/images/testimonial-1.jpg" alt="Client"
                                class="mr-4 h-12 w-12 rounded-full object-cover" />
                            <div>
                                <h4 class="font-semibold">Robert Johnson</h4>
                                <p class="text-sm text-gray-600 dark:text-gray-400">Project Manager, BuildRight
                                    Construction</p>
                            </div>
                        </div>
                    </div>
                    <div class="rounded-lg bg-white p-6 shadow-md dark:bg-gray-800">
                        <div class="mb-4 flex">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-yellow-400" viewBox="0 0 20 20"
                                fill="currentColor">
                                <path
                                    d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                            </svg>
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-yellow-400" viewBox="0 0 20 20"
                                fill="currentColor">
                                <path
                                    d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                            </svg>
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-yellow-400" viewBox="0 0 20 20"
                                fill="currentColor">
                                <path
                                    d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                            </svg>
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-yellow-400" viewBox="0 0 20 20"
                                fill="currentColor">
                                <path
                                    d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                            </svg>
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-yellow-400" viewBox="0 0 20 20"
                                fill="currentColor">
                                <path
                                    d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                            </svg>
                        </div>
                        <p class="mb-4 italic text-gray-600 dark:text-gray-400">"The technical expertise of the Qalcuity
                            team is impressive. They helped us develop a custom mix for our challenging foundation work
                            that exceeded our expectations."</p>
                        <div class="flex items-center">
                            <img src="/images/testimonial-2.jpg" alt="Client"
                                class="mr-4 h-12 w-12 rounded-full object-cover" />
                            <div>
                                <h4 class="font-semibold">Sarah Williams</h4>
                                <p class="text-sm text-gray-600 dark:text-gray-400">Chief Engineer, Metro Development
                                </p>
                            </div>
                        </div>
                    </div>
                    <div class="rounded-lg bg-white p-6 shadow-md dark:bg-gray-800">
                        <div class="mb-4 flex">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-yellow-400" viewBox="0 0 20 20"
                                fill="currentColor">
                                <path
                                    d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                            </svg>
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-yellow-400" viewBox="0 0 20 20"
                                fill="currentColor">
                                <path
                                    d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                            </svg>
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-yellow-400" viewBox="0 0 20 20"
                                fill="currentColor">
                                <path
                                    d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                            </svg>
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-yellow-400" viewBox="0 0 20 20"
                                fill="currentColor">
                                <path
                                    d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                            </svg>
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-yellow-400" viewBox="0 0 20 20"
                                fill="currentColor">
                                <path
                                    d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                            </svg>
                        </div>
                        <p class="mb-4 italic text-gray-600 dark:text-gray-400">"As a small residential contractor, I
                            appreciate how Qalcuity treats every customer with the same level of service regardless of
                            order size. Their concrete quality is consistently excellent."</p>
                        <div class="flex items-center">
                            <img src="/images/testimonial-3.jpg" alt="Client"
                                class="mr-4 h-12 w-12 rounded-full object-cover" />
                            <div>
                                <h4 class="font-semibold">Michael Chen</h4>
                                <p class="text-sm text-gray-600 dark:text-gray-400">Owner, Chen Home Builders</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section id="contact" class="bg-blue-600 py-16 text-white dark:bg-blue-800">
            <div class="container mx-auto px-4">
                <div class="grid grid-cols-1 gap-12 md:grid-cols-2">
                    <div>
                        <h2 class="mb-6 text-3xl font-bold">Contact Us</h2>
                        <p class="mb-8">Ready to start your project with premium concrete? Contact us today for a quote
                            or to discuss your specific requirements.</p>
                        <div class="mb-6 flex items-start">
                            <svg xmlns="http://www.w3.org/2000/svg" class="mr-4 h-6 w-6" fill="none" viewBox="0 0 24 24"
                                stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z" />
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
                            </svg>
                            <div>
                                <h3 class="mb-1 font-semibold">Address</h3>
                                <p>123 Concrete Way, Industrial District<br />Metropolis, MP 12345</p>
                            </div>
                        </div>
                        <div class="mb-6 flex items-start">
                            <svg xmlns="http://www.w3.org/2000/svg" class="mr-4 h-6 w-6" fill="none" viewBox="0 0 24 24"
                                stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
                            </svg>
                            <div>
                                <h3 class="mb-1 font-semibold">Phone</h3>
                                <p>(555) 123-4567</p>
                                <p>Toll Free: 1-800-CONCRETE</p>
                            </div>
                        </div>
                        <div class="mb-6 flex items-start">
                            <svg xmlns="http://www.w3.org/2000/svg" class="mr-4 h-6 w-6" fill="none" viewBox="0 0 24 24"
                                stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                            </svg>
                            <div>
                                <h3 class="mb-1 font-semibold">Email</h3>
                                <p>info@qalcuityconcrete.com</p>
                                <p>sales@qalcuityconcrete.com</p>
                            </div>
                        </div>
                        <div class="flex items-start">
                            <svg xmlns="http://www.w3.org/2000/svg" class="mr-4 h-6 w-6" fill="none" viewBox="0 0 24 24"
                                stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
                            </svg>
                            <div>
                                <h3 class="mb-1 font-semibold">Business Hours</h3>
                                <p>Monday - Friday: 7:00 AM - 5:00 PM</p>
                                <p>Saturday: 8:00 AM - 12:00 PM</p>
                                <p>Sunday: Closed</p>
                            </div>
                        </div>
                    </div>
                    <div>
                        <form class="rounded-lg bg-white p-6 shadow-md dark:bg-gray-800">
                            <h3 class="mb-6 text-xl font-semibold text-gray-800 dark:text-white">Request a Quote</h3>
                            <div class="mb-4 grid grid-cols-1 gap-4 sm:grid-cols-2">
                                <div>
                                    <label for="first_name"
                                        class="mb-2 block text-sm font-medium text-gray-700 dark:text-gray-300">First
                                        Name</label>
                                    <input type="text" id="first_name"
                                        class="w-full rounded-md border border-gray-300 px-3 py-2 focus:border-blue-500 focus:outline-none dark:border-gray-600 dark:bg-gray-700" />
                                </div>
                                <div>
                                    <label for="last_name"
                                        class="mb-2 block text-sm font-medium text-gray-700 dark:text-gray-300">Last
                                        Name</label>
                                    <input type="text" id="last_name"
                                        class="w-full rounded-md border border-gray-300 px-3 py-2 focus:border-blue-500 focus:outline-none dark:border-gray-600 dark:bg-gray-700" />
                                </div>
                            </div>
                            <div class="mb-4">
                                <label for="email"
                                    class="mb-2 block text-sm font-medium text-gray-700 dark:text-gray-300">Email</label>
                                <input type="email" id="email"
                                    class="w-full rounded-md border border-gray-300 px-3 py-2 focus:border-blue-500 focus:outline-none dark:border-gray-600 dark:bg-gray-700" />
                            </div>
                            <div class="mb-4">
                                <label for="phone"
                                    class="mb-2 block text-sm font-medium text-gray-700 dark:text-gray-300">Phone</label>
                                <input type="tel" id="phone"
                                    class="w-full rounded-md border border-gray-300 px-3 py-2 focus:border-blue-500 focus:outline-none dark:border-gray-600 dark:bg-gray-700" />
                            </div>
                            <div class="mb-4">
                                <label for="project_type"
                                    class="mb-2 block text-sm font-medium text-gray-700 dark:text-gray-300">Project
                                    Type</label>
                                <select id="project_type"
                                    class="w-full rounded-md border border-gray-300 px-3 py-2 focus:border-blue-500 focus:outline-none dark:border-gray-600 dark:bg-gray-700">
                                    <option value="">Select Project Type</option>
                                    <option value="residential">Residential</option>
                                    <option value="commercial">Commercial</option>
                                    <option value="industrial">Industrial</option>
                                    <option value="infrastructure">Infrastructure</option>
                                    <option value="other">Other</option>
                                </select>
                            </div>
                            <div class="mb-4">
                                <label for="message"
                                    class="mb-2 block text-sm font-medium text-gray-700 dark:text-gray-300">Project
                                    Details</label>
                                <textarea id="message" rows="4"
                                    class="w-full rounded-md border border-gray-300 px-3 py-2 focus:border-blue-500 focus:outline-none dark:border-gray-600 dark:bg-gray-700"></textarea>
                            </div>
                            <button type="submit"
                                class="w-full rounded-md bg-blue-600 px-4 py-2 font-medium text-white hover:bg-blue-700 dark:bg-blue-500 dark:hover:bg-blue-600">Submit
                                Request</button>
                        </form>
                    </div>
                </div>
            </div>
        </section>

        <!-- Map Section -->
        <section class="py-16">
            <div class="container mx-auto px-4">
                <div class="mb-8 text-center">
                    <h2 class="mb-4 text-3xl font-bold">Find Us</h2>
                    <p class="mx-auto max-w-2xl text-gray-600 dark:text-gray-400">Our concrete plant is conveniently
                        located to serve the entire metropolitan area and surrounding regions.</p>
                </div>
                <div class="h-96 w-full overflow-hidden rounded-lg shadow-md">
                    <!-- Replace with actual map embed code -->
                    <div class="h-full w-full bg-gray-300 flex items-center justify-center">
                        <p class="text-gray-600">Interactive Map Would Be Embedded Here</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- CTA Section -->
        <section class="bg-gray-100 py-16 dark:bg-gray-800">
            <div class="container mx-auto px-4 text-center">
                <h2 class="mb-6 text-3xl font-bold">Ready to Start Your Project?</h2>
                <p class="mx-auto mb-8 max-w-2xl text-gray-600 dark:text-gray-400">Contact us today to discuss your
                    concrete needs and get a competitive quote for your project.</p>
                <div class="flex flex-col items-center justify-center space-y-4 sm:flex-row sm:space-x-4 sm:space-y-0">
                    <a href="#contact"
                        class="rounded-md bg-blue-600 px-6 py-3 font-semibold text-white hover:bg-blue-700 dark:bg-blue-500 dark:hover:bg-blue-600">Request
                        a Quote</a>
                    <a href="tel:5551234567"
                        class="rounded-md border border-blue-600 px-6 py-3 font-semibold text-blue-600 hover:bg-blue-600 hover:text-white dark:border-blue-500 dark:text-blue-400 dark:hover:bg-blue-500 dark:hover:text-white">Call
                        Us: (555) 123-4567</a>
                </div>
            </div>
        </section>

        <!-- Footer -->
        <footer class="bg-gray-800 py-12 text-white dark:bg-gray-900">
            <div class="container mx-auto px-4">
                <div class="grid grid-cols-1 gap-8 md:grid-cols-2 lg:grid-cols-4">
                    <div>
                        <div class="mb-4 flex items-center">
                            <svg xmlns="http://www.w3.org/2000/svg" class="mr-2 h-8 w-8 text-blue-400"
                                viewBox="0 0 20 20" fill="currentColor">
                                <path fill-rule="evenodd"
                                    d="M9.504 1.132a1 1 0 01.992 0l1.75 1a1 1 0 11-.992 1.736L10 3.152l-1.254.716a1 1 0 11-.992-1.736l1.75-1zM5.618 4.504a1 1 0 01-.372 1.364L5.016 6l.23.132a1 1 0 11-.992 1.736L4 7.723V8a1 1 0 01-2 0V6a.996.996 0 01.52-.878l1.734-.99a1 1 0 011.364.372zm8.764 0a1 1 0 011.364-.372l1.733.99A1.002 1.002 0 0118 6v2a1 1 0 11-2 0v-.277l-.254.145a1 1 0 11-.992-1.736l.23-.132-.23-.132a1 1 0 01-.372-1.364zm-7 4a1 1 0 011.364-.372L10 8.848l1.254-.716a1 1 0 11.992 1.736L11 10.58V12a1 1 0 11-2 0v-1.42l-1.246-.712a1 1 0 01-.372-1.364zM3 11a1 1 0 011 1v1.42l1.246.712a1 1 0 11-.992 1.736l-1.75-1A1 1 0 012 14v-2a1 1 0 011-1zm14 0a1 1 0 011 1v2a1 1 0 01-.504.868l-1.75 1a1 1 0 11-.992-1.736L16 13.42V12a1 1 0 011-1zm-9.618 5.504a1 1 0 011.364-.372l.254.145V16a1 1 0 112 0v.277l.254-.145a1 1 0 11.992 1.736l-1.735.992a.995.995 0 01-1.022 0l-1.735-.992a1 1 0 01-.372-1.364z"
                                    clip-rule="evenodd" />
                            </svg>
                            <span class="text-xl font-bold">Qalcuity Concrete</span>
                        </div>
                        <p class="mb-4 text-gray-400">Providing premium liquid concrete solutions for all your
                            construction needs since 2005.</p>
                        <div class="flex space-x-4">
                            <a href="#" class="text-gray-400 hover:text-white">
                                <svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                                    <path fill-rule="evenodd"
                                        d="M22 12c0-5.523-4.477-10-10-10S2 6.477 2 12c0 4.991 3.657 9.128 8.438 9.878v-6.987h-2.54V12h2.54V9.797c0-2.506 1.492-3.89 3.777-3.89 1.094 0 2.238.195 2.238.195v2.46h-1.26c-1.243 0-1.63.771-1.63 1.562V12h2.773l-.443 2.89h-2.33v6.988C18.343 21.128 22 16.991 22 12z"
                                        clip-rule="evenodd" />
                                </svg>
                            </a>
                            <a href="#" class="text-gray-400 hover:text-white">
                                <svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                                    <path fill-rule="evenodd"
                                        d="M12 6.865a5.135 5.135 0 110 10.27 5.135 5.135 0 010-10.27zm0 1.802a3.333 3.333 0 100 6.666 3.333 3.333 0 000-6.666z"
                                        clip-rule="evenodd" />
                                    <path
                                        d="M16.5 12a4.5 4.5 0 11-9 0 4.5 4.5 0 019 0zm-9.007-5.559a1.5 1.5 0 10-3 0v.069l.002.083a1.5 1.5 0 001.5 1.348h1.499l-.001-.15-.001-.15.001-.082a1.5 1.5 0 00-1.501-1.5H7.5l-.001-.001z" />
                                </svg>
                            </a>
                            <a href="#" class="text-gray-400 hover:text-white">
                                <svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                                    <path
                                        d="M8.29 20.251c7.547 0 11.675-6.253 11.675-11.675 0-.178 0-.355-.012-.53A8.348 8.348 0 0022 5.92a8.19 8.19 0 01-2.357.646 4.118 4.118 0 001.804-2.27 8.224 8.224 0 01-2.605.996 4.107 4.107 0 00-6.993 3.743 11.65 11.65 0 01-8.457-4.287 4.106 4.106 0 001.27 5.477A4.072 4.072 0 012.8 9.713v.052a4.105 4.105 0 003.292 4.022 4.095 4.095 0 01-1.853.07 4.108 4.108 0 003.834 2.85A8.233 8.233 0 012 18.407a11.616 11.616 0 006.29 1.84" />
                                </svg>
                            </a>
                            <a href="#" class="text-gray-400 hover:text-white">
                                <svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                                    <path fill-rule="evenodd"
                                        d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"
                                        clip-rule="evenodd" />
                                </svg>
                            </a>
                            <a href="#" class="text-gray-400 hover:text-white">
                                <svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                                    <path fill-rule="evenodd"
                                        d="M19.812 5.418c.861.23 1.538.907 1.768 1.768C21.998 8.746 22 12 22 12s0 3.255-.418 4.814a2.504 2.504 0 0 1-1.768 1.768c-1.56.419-7.814.419-7.814.419s-6.255 0-7.814-.419a2.505 2.505 0 0 1-1.768-1.768C2 15.255 2 12 2 12s0-3.255.417-4.814a2.507 2.507 0 0 1 1.768-1.768C5.744 5 11.998 5 11.998 5s6.255 0 7.814.418ZM15.194 12 10 15V9l5.194 3Z"
                                        clip-rule="evenodd" />
                                </svg>
                            </a>
                        </div>
                    </div>
                    <div>
                        <h3 class="mb-4 text-lg font-semibold">Quick Links</h3>
                        <ul class="space-y-2">
                            <li><a href="#" class="text-gray-400 hover:text-white">Home</a></li>
                            <li><a href="#products" class="text-gray-400 hover:text-white">Products</a></li>
                            <li><a href="#services" class="text-gray-400 hover:text-white">Services</a></li>
                            <li><a href="#about" class="text-gray-400 hover:text-white">About Us</a></li>
                            <li><a href="#contact" class="text-gray-400 hover:text-white">Contact</a></li>
                        </ul>
                    </div>
                    <div>
                        <h3 class="mb-4 text-lg font-semibold">Products</h3>
                        <ul class="space-y-2">
                            <li><a href="#" class="text-gray-400 hover:text-white">Ready-Mix Concrete</a></li>
                            <li><a href="#" class="text-gray-400 hover:text-white">High Strength Concrete</a></li>
                            <li><a href="#" class="text-gray-400 hover:text-white">Decorative Concrete</a></li>
                            <li><a href="#" class="text-gray-400 hover:text-white">Specialty Mixes</a></li>
                            <li><a href="#" class="text-gray-400 hover:text-white">Concrete Additives</a></li>
                        </ul>
                    </div>
                    <div>
                        <h3 class="mb-4 text-lg font-semibold">Newsletter</h3>
                        <p class="mb-4 text-gray-400">Subscribe to our newsletter for the latest updates and offers.</p>
                        <form class="flex">
                            <input type="email" placeholder="Your email"
                                class="w-full rounded-l-md border-gray-600 bg-gray-700 px-3 py-2 text-white placeholder-gray-400 focus:border-blue-500 focus:outline-none" />
                            <button type="submit"
                                class="rounded-r-md bg-blue-600 px-4 py-2 text-white hover:bg-blue-700">Subscribe</button>
                        </form>
                    </div>
                </div>
                <div class="mt-8 border-t border-gray-700 pt-8 text-center">
                    <p class="text-gray-400">&copy; 2023 Qalcuity Concrete. All rights reserved.</p>
                </div>
            </div>
        </footer>
    </div>
</template>
