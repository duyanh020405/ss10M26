<template>
  <div>
    <h1>Bt6</h1>
    <p>Count = {{ a }}</p>
    <button @click="c">Tang count</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const a = ref(0)
const c = ()=>{
    a.value++
    document.title = a.value
}
</script>

<style>

</style>