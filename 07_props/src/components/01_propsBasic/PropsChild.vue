<script setup>
import {inject} from 'vue';

const {message} = inject('data');   //inject 주입하다
const darkMode = inject("darkmode");
const darkState = inject("darkState");
</script>

<template>
    <h1>전달 받은 props : {{ message }}</h1>
    <button @click="darkMode">자식의 DarkMode + {{ darkState }}</button>
</template>