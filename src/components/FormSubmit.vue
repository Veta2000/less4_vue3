<template>
    <form @submit.prevent="handleSubmit">
      <input v-model="formData.name" type="text" placeholder="Введите имя" required />
      <input v-model.number="formData.age" type="number" placeholder="Введите возраст" required />
      <button type="submit">Отправить</button>
    </form>
    <p v-if="error">{{ error }}</p>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const formData = ref({ name: '', age: null });
  const error = ref('');
  
  function handleSubmit() {
    if (!formData.value.name || formData.value.age < 18) {
      error.value = 'Пожалуйста, введите корректное имя и возраст (18 лет и старше).';
    } else {
      error.value = '';
      console.log('Форма отправлена:', formData.value);
    }
  }
  </script>
  
  <style scoped>
  </style>
  