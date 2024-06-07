<script setup>
    import {ref} from 'vue';
    import DynamicChild from './DynamicChild.vue';
    const dynamicName = ref("name");
</script>

<template>
    <div>
        <h1>DynamicSlot : </h1>
        <input v-model="dynamicName"/>
        <DynamicChild>
            <template #[dynamicName]>
                {{ dynamicName }}
            </template>
        </DynamicChild>
    </div>
</template>

<style scoped>
    .parentsContainer{
        display: flex;
        flex-direction: column;
        align-items: center;
        border: 1px solid;
    }
</style>