<script>
import axios from 'axios';
import { BASE_URL } from '../data/data';
export default {
  name: 'ProjectDetail',
  data() {
    return {
      project: {}
    }
  },
  methods: {
    getApi() {
      axios.get(BASE_URL + 'projects/' + this.$route.params.slug)
        .then(res => {
          this.project = res.data;
          console.log(res.data);
        })

    }
  },
  mounted() {
    //console.log(this.$route.params.slug);
    this.getApi();
  }
}

</script>



<template>
  <!-- <div>
        <img :src="project.cover_image" :alt="project.name">
    </div> -->
  <h1>{{ project.name }}</h1>
  <h3>{{ project.client_name }}</h3>
  <p>{{ project.summary }}</p>
  <div v-if="project.type">Type: {{ project.type.name }}</div>
  <div v-if="project.technologies" class="tech-box">
    <div v-for="technology in project.technologies" :key="technology.id">{{ technology.name }}</div>
  </div>
</template>


<style lang="scss" scoped>
img {
  margin-bottom: 20px;
}

h1 {
  color: black;
}

h3 {
  padding-bottom: 10px;
}
</style>
