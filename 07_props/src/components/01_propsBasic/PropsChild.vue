<script setup>
import {inject} from 'vue';

const message = inject('message');   //inject 주입하다 = ("전달한 key값");
const darkState = inject("childDark");

function darkMode() {
    darkState.value = !darkState.value  //객체타입의 프록시 , 수학적이지 않고 문학적이네   
}
</script>

<template>
    <div class="box">
        <h3>전달 받은 props : {{ message }}</h3>
        <h1>다크모드 활성화 여부 : {{ darkState }}</h1>
    </div>
</template>

<style>
.box {
    border: 1px dotted black;
}
</style>