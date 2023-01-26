
<script>
import axios from 'axios';
import { store } from './data/store';
import ProjectCard from './components/ProjectCard.vue';
export default {
  name: 'App',
data() {
    store
  },
  components: {ProjectCard},
  methods: {
    getApi() {
      axios.get(store.baseUrl + 'projects')
        .then(result => {
          store.projects = result.data.projects
          console.log(store.projects)
        })
    }
  },
  mounted() {
    this.getApi();
  }
}
</script>

<template>
  <ProjectCard />
</template>


<style lang="scss">
@use './style/general';

</style>