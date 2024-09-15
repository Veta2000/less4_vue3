<template>
    <div>
      <input v-model="filter" placeholder="Фильтр" />
      <ul>
        <li v-for="item in filteredItems" :key="item">{{ item }}</li>
      </ul>
    </div>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue';
  
  const items = ref([
    'Калейдоскоп', 'Доминанта', 'Асимметрия', 'Парадигма', 'Интерпретация', 'Феноменология', 'Эффемерность', 'Амбивалентность', 'Гипотеза', 'Синергия'
  ]);
  
  const filter = ref('');
  
  const filteredItems = computed(() => {
    const filterLower = filter.value.toLowerCase();
    return items.value.filter(item => item.toLowerCase().includes(filterLower));
  });
  </script>
  
  <style scoped>

  </style>
  