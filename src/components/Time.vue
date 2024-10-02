<template>
  <div>
    <h1>Time :{{ time }}</h1>
  </div>
</template>

<script setup>
import { onBeforeMount, onBeforeUnmount, onBeforeUpdate, onMounted, onUnmounted, onUpdated ,ref} from "vue";

onBeforeMount(()=>{
    console.log("beforeMount");
})
// onMounted(()=>{
//     setInterval(()=>{
//         time.value++
//     },1)
//     console.log("OnMount");
// })
onBeforeUpdate(()=>{
    console.log("UpdateTime"); 
})
onUpdated(()=>{
    console.log("Updateed");
})

// giai doan unMount

onBeforeUnmount(()=>{
    clearInterval(time)
    console.log("before Unmount");
})
onUnmounted(()=>{
    console.log("unmounted");
})
const time = ref(0)
</script>

<style>

</style>