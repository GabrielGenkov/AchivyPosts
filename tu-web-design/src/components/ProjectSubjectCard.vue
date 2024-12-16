<template>
  <div class="card">
    <img :src="imageSrc" alt="Project Image" />
    <h3>{{ name }}</h3>
    <p>{{ description }}</p>
    <button @click="deleteProjectSubject">Delete</button>
  </div>
</template>

<script setup>
const props = defineProps(['name', 'imageSrc', 'description']);
const emit = defineEmits(['deleteProjectSubject']);

function deleteProjectSubject() {
  emit('deleteProjectSubject');
}
</script>