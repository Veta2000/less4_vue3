<template>
    <ul>
      <li v-for="(object, index) in objects" :key="index">
        {{ object.name }}
        <ul>
          <li v-for="(item, subIndex) in object.items" :key="subIndex">{{ item }}</li>
        </ul>
      </li>
    </ul>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const objects = ref([
    { name: 'Объект 1', items: ['Элемент 1.1', 'Элемент 1.2'] },
    { name: 'Объект 2', items: ['Элемент 2.1', 'Элемент 2.2'] },
    { name: 'Объект 3', items: ['Элемент 3.1', 'Элемент 3.2'] },
  ]);
  </script>
  
  <style scoped>

  </style>
  