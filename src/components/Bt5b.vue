<template>
  <h3>Component Con</h3>
</template>

<script setup>
import { onBeforeUnmount, onUnmounted, ref } from 'vue';
onBeforeUnmount(()=>{
    console.log("Component is about to be unmounted");
})
onUnmounted(()=>{
    console.log("Component has been unmounted");
})
</script>

<style>

</style>