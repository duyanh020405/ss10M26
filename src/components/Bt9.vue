<template>
  <div>
    <h1>Bt 9</h1>
    <P>Dem so : {{ a }}</P>
  </div>
</template>

<script setup>
import { onMounted,ref } from 'vue';
const a= ref(0)
onMounted(()=>{
   setInterval(()=>{
    a.value++
   },1000)
})
</script>

<style>

</style>