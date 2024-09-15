<template>
    <div>
      <button @click="toggleTheme">Переключить тему</button>
      <p>Текущая тема: {{ currentTheme }}</p>
    </div>
  </template>
  
  <script setup>
  import { ref, defineEmits } from 'vue';
  
  const currentTheme = ref('Светлая');
  const emit = defineEmits(['toggle-theme']);
  
  function toggleTheme() {
    emit('toggle-theme');
    currentTheme.value = currentTheme.value === 'Светлая' ? 'Темная' : 'Светлая';
  }
  </script>
  
  <style scoped>
  button {
    margin-bottom: 10px;
  }
  </style>
  