<template>
    <div>
      <h1>Bai4</h1>
      <Bt4bVue :name="age" v-if="isShow"></Bt4bVue>
      <p>Age: {{ age }}</p>
      <button @click="up">Increase age</button>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import Bt4bVue from './Bt4b.vue';
  
  // Khởi tạo biến age và isShow
  const age = ref(0);
  const isShow = ref(false);
  const up = () => {
    age.value++;
    isShow.value = true;
    setTimeout(() => {
      isShow.value = false; 
    }, 1000);
  };
  </script>
