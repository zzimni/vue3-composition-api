<script setup>
// option api -> composition api
// - setup 기능으로 스크립트 작성 규칙을 단순화
// - 옵션을 따로 구분할 필요없이 한 곳에서 작성
// - ref()로 상태변수 관리
// - defineProps로 prop 관리

import { ref, onMounted } from "vue";

let count = ref(0); // 상태변수 초기값(state)
let title = "Hello Vue"; // 일반 변수

onMounted(() => {
  // composition api에서는 라이프사이클 훅을 사용하려면 모듈을 import부터 해줘야함
  console.log("mounted");
});

const increaseCount = () => {
  count.value++; // count = ref(0); 으로 관리되고있으므로 실제 값은 ref함수 안에 들어있기 때문에 count 숫자를 변경할 때는 그냥 count가 아닌 count.value로 접근해야함 (함수에서 value라는 값을 가져와야한다)
};
</script>

<template>
  <div>
    <h1>{{ title }}</h1>
    <button @click="increaseCount">count++</button>
    <p>{{ count }}</p>
  </div>
</template>

<style scoped></style>
