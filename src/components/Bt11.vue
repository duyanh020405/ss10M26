<template>
    <div class="traffic-light">
      <div :class="['light', { red: currentLight === 'red' }]"></div>
      <div :class="['light', { yellow: currentLight === 'yellow' }]"></div>
      <div :class="['light', { green: currentLight === 'green' }]"></div>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted, onUnmounted } from 'vue';
  const currentLight = ref('red'); 
  let intervalId = null;
  const changeLight = () => {
    if (currentLight.value === 'red') {
      currentLight.value = 'green'; 
    } else if (currentLight.value === 'green') {
      currentLight.value = 'yellow'; 
    } else {
      currentLight.value = 'red'; 
    }
  };
  const startTrafficLight = () => {
    changeLight(); 
    intervalId = setInterval(() => {
      changeLight();
    }, getCurrentLightDuration()); 
  };
  
  const getCurrentLightDuration = () => {
    switch (currentLight.value) {
      case 'red':
        return 40000; // Đèn đỏ: 40 giây
      case 'green':
        return 60000; // Đèn xanh: 60 giây
      case 'yellow':
        return 3000; // Đèn vàng: 3 giây
      default:
        return 0;
    }
  };

  onMounted(() => {
    startTrafficLight();
  });

  onUnmounted(() => {
    clearInterval(intervalId);
  });
  </script>
  
  <style scoped>
  .traffic-light {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
    width: 100px;
    height: 300px;
    background-color: #333;
    border-radius: 10px;
    padding: 10px;
  }
  
  .light {
    width: 80px;
    height: 80px;
    border-radius: 50%;
    opacity: 0.3; /* Đặt độ mờ mặc định */
  }
  
  .red {
    background-color: red;
    opacity: 1; /* Đèn đỏ sáng */
  }
  
  .yellow {
    background-color: yellow;
    opacity: 1; /* Đèn vàng sáng */
  }
  
  .green {
    background-color: green;
    opacity: 1; /* Đèn xanh sáng */
  }
  </style>
  