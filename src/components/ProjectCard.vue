<script>
import { store } from '../data/store';
export default {
name: 'ProjectCard',
data() {
  return {
    store
  }
}
}
</script>

<template>
    <h1>Projects List</h1>
    <div v-for="project in store.projects" :key="project.id">
      <h3>{{ project.name }}</h3>
      <p>{{ project.summary }}</p>
    </div>
</template>


<style lang="scss" scoped>

</style>