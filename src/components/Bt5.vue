<template>
  <div>
    <h1>Bai 5</h1>
    <div v-if="a">
        <Bt5b></Bt5b>
    </div>
    <button @click="show">Show</button>


  </div>
</template>

<script setup>
import { onBeforeUnmount, onUnmounted, ref } from 'vue';
import Bt5b from './Bt5b.vue';
const a = ref(false)
const show=()=>{
    a.value =! a.value
}

</script>

<style>

</style>