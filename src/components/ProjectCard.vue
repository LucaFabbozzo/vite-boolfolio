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
  <div class="container">
    <h1 class="title">My Projects List</h1>
    <div class="project-list" v-for="project in store.projects" :key="project.id">
      <h3>{{ project.name }}</h3>
      <p>{{ project.summary }}</p>
    </div>
  </div>
</template>


<style lang="scss" scoped>

</style>