<template>
  <div :class="currentTheme" id="app">
    <ThemeSwitcher @toggle-theme="toggleTheme" />
    <EventStorage />
    <FormSubmit />
    <DynamicEventHandlers />
    <DynamicListStyles />
    <DynamicTable />
    <NestedObjectsList />
    <PaginatedList />
    <FilteredList />
  </div>
</template>

<script setup>
import { ref } from 'vue';

import EventStorage from './components/EventStorage.vue';
import FormSubmit from './components/FormSubmit.vue';
import DynamicEventHandlers from './components/DynamicEventHandlers.vue';
import DynamicListStyles from './components/DynamicListStyles.vue';
import ThemeSwitcher from './components/ThemeSwitcher.vue';
import DynamicTable from './components/DynamicTable.vue';
import NestedObjectsList from './components/NestedObjectsList.vue';
import PaginatedList from './components/PaginatedList.vue';
import FilteredList from './components/FilteredList.vue';

const currentTheme = ref('light-theme');

function toggleTheme() {
  currentTheme.value = currentTheme.value === 'light-theme' ? 'dark-theme' : 'light-theme';
}
</script>

<style>
.light-theme {
  background-color: white;
  color: black;
}

.dark-theme {
  background-color: black;
  color: white;
}

#app {
  transition: background-color 0.3s, color 0.3s;
}
</style>
