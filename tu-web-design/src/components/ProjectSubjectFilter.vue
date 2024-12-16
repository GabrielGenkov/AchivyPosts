<template>
  <input type="text" v-model="filterText" @input="updateFilter" placeholder="Filter by name" />
</template>

<script setup>
import { ref } from 'vue';

const filterText = ref('');
const emit = defineEmits(['filterUpdated']);

function updateFilter() {
  emit('filterUpdated', filterText.value);
}
</script>