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
  <div class="show-box">
    <!-- <img :src="project.cover_image" :alt="project.name"> -->
    <h1>{{ project.name }}</h1>
    <h3>{{ project.client_name }}</h3>
    <p>{{ project.summary }}</p>
    <div v-if="project.type" class="type">Type: {{ project.type.name }}</div>
    <div v-if="project.technologies" class="tech-box">
      <div v-for="technology in project.technologies" :key="technology.id" class="tech">{{ technology.name }}</div>
    </div>
  </div>
</template>


<style lang="scss" scoped>
.show-box {
  padding: 35px;

  img {
    margin-bottom: 20px;
  }

  h1 {
    color: black;
  }

  h3 {
    padding-bottom: 10px;
  }

  p {
    padding-bottom: 15px;
  }
}

.type {
  padding-bottom: 15px;
}

.tech-box {
  .tech {
    display: inline-block;
    margin-right: 15px;
    padding: 10px 8px;
    border: 1px solid black;
    border-radius: 5px;
    background-color: #cacaca;
  }
}
</style>
