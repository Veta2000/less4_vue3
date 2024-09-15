<template>
    <div>
      <button @click="currentHandler">Нажми меня</button>
      <button @click="toggleHandler">Переключить обработчик</button>
      <p>Текущий обработчик: {{ currentHandlerName }}</p>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const handlerA = () => alert('Обработчик A');
  const handlerB = () => alert('Обработчик B');
  const useHandlerA = ref(true);
  
  const currentHandler = ref(handlerA);
  const currentHandlerName = ref('Обработчик A');
  
  function toggleHandler() {
    useHandlerA.value = !useHandlerA.value;
    if (useHandlerA.value) {
      currentHandler.value = handlerA;
      currentHandlerName.value = 'Обработчик A';
    } else {
      currentHandler.value = handlerB;
      currentHandlerName.value = 'Обработчик B';
    }
  }
  </script>
  
  <style scoped>
  </style>
  