<template>
  <div>
    <ProjectSubjectCard
      v-for="(subject, index) in subjects"
      :key="index"
      :name="subject.name"
      :imageSrc="subject.imageSrc"
      :description="subject.description"
      @deleteProjectSubject="deleteSubject(index)"
    />
  </div>
</template>

<script setup>
import ProjectSubjectCard from './ProjectSubjectCard.vue';

const props = defineProps(['subjects']);
const emit = defineEmits(['deleteSubject']);

function deleteSubject(index) {
  emit('deleteSubject', index);
}
</script>