<template>
    <div>
      <Time></Time>
      Count {{count}}
      <input type="text" v-model="inputValue">
      <button @click="tang">Count+</button>
    </div>
  </template>
  
  <script setup>
  import {onBeforeMount,onBeforeUpdate,onMounted, onUpdated} from 'vue'
  import {ref} from 'vue'
  // onBeforeMount -1 , onMount -2
  onBeforeMount(() => {
    console.log("Component before mount");
    // count.value = 5
  })
  onMounted(() => {
    console.log("Component mouted");
    // count.value =6
  })
  
  // cac phuong thuc trong giai doan update
  onBeforeUpdate(()=>{
    document.title =inputValue.value
    console.log("Before update");
    
  })
  onUpdated(()=>{
  console.log("Component Updated");
  
  })
  const inputValue = ref('')
  const count = ref(0)
  const tang =()=>{
    count.value++
  }
  // Cac phuong thuc trong giai doan UnMount
//   import Time from './components/Time.vue'
  </script>
  
  <style>
  
  </style>