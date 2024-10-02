<template>
    <div>
        <h1>Bai3</h1>
      <p>Current Company: {{ b }}</p>
      <p>Age : {{ c }}</p>
      <button @click="randomize">Random</button>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  const d = ref([1, 2, 3, 4, 5, 6, 7, 8, 9]);
  const a = ref(["Rikkei Academy", "Rikkei Education", "Rikkei Fukuoka"]);
  const c = ref(d.value[Math.floor(Math.random() * d.value.length)]);
  const b = ref(a.value[Math.floor(Math.random() * a.value.length)]);
  const randomize = () => {
    c.value = d.value[Math.floor(Math.random() * d.value.length)];
    b.value = a.value[Math.floor(Math.random() * a.value.length)];
  };
  </script>
  
  <style>
  </style>
  