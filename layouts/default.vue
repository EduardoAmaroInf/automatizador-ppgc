<template>
    <div>
        <Header />
        <slot />
        <Footer />
    </div>
</template>

<script setup>
import Footer from '~/components/layout/Footer.vue';
import Header from '~/components/layout/Header.vue'
</script>
