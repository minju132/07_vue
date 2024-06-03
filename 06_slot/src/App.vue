<script setup>
import MyComponent from './components/01_component/MyComponent.vue';
import parents from './components/02_slotintro/SlotParents.vue';
import NamedParents from './components/03_slotnamed/NamedParents.vue';
import DynamicParent from './components/04_dynamicslot/DynamicParent.vue';
</script>

<!--
  slot
  슬롯(slot)은 vue 컴포넌트에서 콘텐츠를 전달하는 메커니즘으로 부모 컴포넌트에서 자식 컴포넌트로 데이터나 구조를 전달하는데 사용된다.
  슬롯을 사용하면 부모 컴포넌트에서 자식 컴포넌트의 일부를 동적으로 결정할 수 있으며, 재사용 가능한 컴포넌트를 작성하는데 도움이 된다.
  일반적으로 컴포넌트 내의 마크업에서 <slot> 요소를 사용하여 슬롯을 정의하며 이는 자식 컴포넌트에서 해당 영역에 부모 컴포넌트로부터
    전달된 콘텐츠를 표시하도록 지시한다.
-->
<template>
  <div>
    <h1>component Container</h1>
    <MyComponent/>
  </div>
  <main>
      <parents/>
      <NamedParents/>
      <DynamicParent/>
  </main>
</template>

<style scoped>
/* css를 정의하는 스코프 */
</style>
