<template>
    <div>
      <button @click="saveClickTime">Сохрани время</button>
      <ul>
        <li v-for="(time, index) in clickTimes" :key="index">{{ time }}</li>
      </ul>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const clickTimes = ref([]);
  
  function saveClickTime() {
    const currentTime = new Date().toLocaleTimeString();
    clickTimes.value.push(currentTime);
  }
  </script>
  
  <style scoped>
  button {
    margin-bottom: 10px;
  }
  </style>
  