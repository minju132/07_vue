<script setup>
    import { provide, ref,readonly } from "vue";
    import propsChild from './PropsChild.vue'
    import DarkMode from './DarkMode.vue'
    import ReadProps from "./ReadProps.vue"

    const message = ref("hello")
    const darkState = ref(false);   // 반응형 변수가 바뀔때마다 변수 쪽 화면이 렌더링됨
    const readValue = ref("vue는 재미있다")
    
    // 공급자
    provide("message", message);
    provide("darkState", darkState);
    provide("readValue", readonly(readValue));
    provide("childDark", readonly(darkState));
</script>

<!-- 
    템플릿은 화면에 나올때 자식을 반환하고 템플릿 자신은 사라짐

    : 를 안 쓰고 변수를 입력하면 문자자체인 변수로 받아들임

    prop
    부모에서 자식 컴포넌트로 데이터를 전달하는 경우 우리는 다양한 <slot>을 이용할 수 있었다.
    하지만 slot 의 경우 콘텐츠를 전달하기 위해 사용하는 것으로 단일 데이터를 전달하는 경우 맞지 않으며
    부모에게 전달 받은 데이터를 전달하여 조작하는데도 어려움이 있다.
    이러한 경우 우리는 데이터만 전달하기 위한 용도로 props를 사용할 수 있다.
-->
<template>
    <div :class="{container:true, dark:darkState}">
        props 입력 <input v-model="message"/>        
    </div>
    <propsChild/>
    <br>
    <DarkMode/>
    <ReadProps/>
</template>

<style scoped>
    .container{
        border : 1px solid;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .dark{
        background-color: black;
        color: white;
    }
</style>