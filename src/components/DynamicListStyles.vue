<template>
    <ul>
      <li v-for="(item, index) in items" :key="index" :style="generateStyle(item)">
        {{ item }}
      </li>
    </ul>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const items = ref(['Элемент 1', 'Элемент 2', 'Элемент 3', 'Элемент 4', 'Элемент 5']);
  
  function generateStyle(item) {
    const randomColor = `#${Math.floor(Math.random() * 16777215).toString(16)}`;
    const randomFontSize = `${Math.floor(Math.random() * 10) + 14}px`;
    return {
      backgroundColor: randomColor,
      fontSize: randomFontSize,
      padding: '5px',
      margin: '5px 0',
    };
  }
  </script>
  
  <style scoped>

  </style>
  