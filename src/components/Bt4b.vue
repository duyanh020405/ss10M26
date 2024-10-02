<template>
    <h3>Thong bao: Dữ liệu của 'name' đã thay đổi</h3>
  </template>
  
  <script setup>
  import { onUpdated, defineProps } from 'vue';
  const props = defineProps(["name"]);
  onUpdated(() => {
    console.log("Dữ liệu của 'name' đã thay đổi");
  });
  </script>
  