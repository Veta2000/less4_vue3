<template>
    <div>
      <ul>
        <li v-for="item in paginatedItems" :key="item">{{ item }}</li>
      </ul>
      <button @click="prevPage" :disabled="currentPage === 1">Назад</button>
      <button @click="nextPage" :disabled="currentPage === pageCount">Вперед</button>
    </div>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue';
  
  const items = ref([
    'Элемент 1', 'Элемент 2', 'Элемент 3', 'Элемент 4', 'Элемент 5',
    'Элемент 6', 'Элемент 7', 'Элемент 8', 'Элемент 9', 'Элемент 10',
  ]);
  
  const itemsPerPage = 3;
  const currentPage = ref(1);
  
  const paginatedItems = computed(() => {
    const start = (currentPage.value - 1) * itemsPerPage;
    return items.value.slice(start, start + itemsPerPage);
  });
  
  const pageCount = computed(() => Math.ceil(items.value.length / itemsPerPage));
  
  function prevPage() {
    if (currentPage.value > 1) currentPage.value--;
  }
  
  function nextPage() {
    if (currentPage.value < pageCount.value) currentPage.value++;
  }
  </script>
  
  <style scoped>
  button {
    margin-top: 10px;
  }
  </style>
  