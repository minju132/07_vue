<script setup>
import { onMounted, ref } from "vue";
import { useRouter } from "vue-router";

const route = useRouter();

onMounted(()=>{
    console.log(route.params);
})
</script>

<template>
    <h1>pathVariable : {{ $route.params.id }}</h1>
</template>