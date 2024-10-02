<template>
  <div>
    <h1>Bt2</h1>
    <p>Count :{{ a }}</p>
    <button @click="up">Couter</button>
  </div>
</template>

<script setup>
import { onUpdated, ref } from 'vue';

const a =ref(0)
const up =()=>{
    a.value++    
}
onUpdated(()=>{
    console.log("Du lieu thay doi");
    
})
</script>

<style>

</style>