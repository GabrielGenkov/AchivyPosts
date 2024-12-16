<template>
  <form @submit.prevent="submitForm">
    <div>
      <label for="name">Name:</label>
      <input id="name" v-model="name" required />
    </div>
    <div>
      <label for="image">Image URL:</label>
      <input id="image" v-model="imageSrc" required />
    </div>
    <div>
      <label for="description">Description:</label>
      <textarea id="description" v-model="description" required></textarea>
    </div>
    <button type="submit">Add</button>
  </form>
</template>

<script setup>
import { ref } from 'vue';

const name = ref('');
const imageSrc = ref('');
const description = ref('');
const emit = defineEmits(['addProjectSubject']);

function submitForm() {
  emit('addProjectSubject', { name: name.value, imageSrc: imageSrc.value, description: description.value });
  name.value = '';
  imageSrc.value = '';
  description.value = '';
}
</script>