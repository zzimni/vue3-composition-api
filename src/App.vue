<script setup>
  import { ref, onMounted } from 'vue';

  let count = ref(0); // 상태변수 초기값(state)
  let title = "Hello Vue";

  onMounted(() => {
    console.log('mounted');
  })

  const increaseCount = () => {
    count.value++;
  }
</script>

<template>
  <div>
    <h1>{{ title }}</h1>
    <button @click="increaseCount">count++</button>
    <p>{{ count }}</p>
  </div>
</template>

<style scoped>
</style>
