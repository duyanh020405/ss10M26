<template>
    <div>
      <h1>Bt10</h1>
      <p>Thời gian hiện tại - {{ a }} : {{ b }} : {{ c }}</p>
    </div>
  </template>
  
  <script setup>
  import { onMounted, ref } from 'vue';

  const a = ref(0); 
  const b = ref(0); 
  const c = ref(0); 
  onMounted(() => {
    setInterval(() => {
      c.value++; 
      if (c.value === 60) {
        b.value++;
        c.value = 0;
        if (b.value === 60) {
          a.value++; 
          b.value = 0; 
        }
      }
    }, 1000); 
  });
  </script>
