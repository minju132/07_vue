<script setup>
    import { inject } from 'vue';

    const darkMode = inject("darkmode")
</script>

<template>
    <button @click="darkMode">Vue 다크모드 + {{ darkState }}</button>
</template>