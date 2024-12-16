<template>
  <div>
    <header>
      <h1>Add your new post here!</h1>
    </header>
    <AddProjectSubject @addProjectSubject="addSubject" />
    <ProjectSubjectFilter @filterUpdated="filterSubjects" />
    <ProjectSubjectList
      :subjects="filteredSubjects"
      @deleteSubject="deleteSubject"
    />
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';
import AddProjectSubject from './components/AddProjectSubject.vue';
import ProjectSubjectList from './components/ProjectSubjectList.vue';
import ProjectSubjectFilter from './components/ProjectSubjectFilter.vue';

const subjects = ref([]);
const filterText = ref('');

function addSubject(newSubject) {
  subjects.value.push(newSubject);
}

function deleteSubject(index) {
  subjects.value.splice(index, 1);
}

function filterSubjects(filter) {
  filterText.value = filter;
}

const filteredSubjects = computed(() =>
  subjects.value.filter((subject) =>
    subject.name.toLowerCase().includes(filterText.value.toLowerCase())
  )
);
</script>