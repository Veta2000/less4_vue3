<template>
    <div>
      <input v-model.number="rows" type="number" placeholder="Строки" />
      <input v-model.number="cols" type="number" placeholder="Столбцы" />
      <table>
        <tr v-for="rowIndex in rows" :key="rowIndex">
          <td v-for="colIndex in cols" :key="colIndex">{{ rowIndex }},{{ colIndex }}</td>
        </tr>
      </table>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const rows = ref(3);
  const cols = ref(3);
  </script>
  
  <style scoped>
  table {
    border-collapse: collapse;
    width: 100%;
  }
  
  td {
    border: 1px solid #ddd;
    padding: 8px;
  }
  </style>
  