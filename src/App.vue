<script setup>
import { ref, onMounted, watch } from "vue";
import ChildComp from "./components/ChildComp.vue";

let count = ref(0); // 상태변수 초기값(state)
let title = "Hello Vue";
let color = ref("green");

onMounted(() => {
  console.log("mounted");
});

const increaseCount = () => {
  count.value++;
};

// watch(감시할 상태변수, 함수)
// vue에서부터 import 해줘야함
// color 값이 변경 됐을 때 화살표함수 실행되는 것
watch(color, () => {
  console.log("color 변경");
});
</script>

<template>
  <div>
    <h1 class="red">{{ title }}</h1>
    <button @click="increaseCount">count++</button>
    <p>{{ count }}</p>
    <ChildComp :color="color" bgColor="yellow" />
    <!-- :color="color"을 통해 ChildComp에 color라는 변수에 green이 대입돼서 전달됨 -->
    <button @click="color = 'red'">change color</button>
  </div>
</template>

<style></style>
