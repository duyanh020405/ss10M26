<template>
  <div>
    <h1>Bt7</h1>
    <input type="text" @change="a" v-model="inputValue">
  </div>
</template>

<script setup>
import { ref , onBeforeUpdate } from 'vue';
const inputValue = ref('')
onBeforeUpdate(()=>{
    document.title =inputValue.value
    console.log("Before update");
    
  })
</script>

<style>

</style>