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
  <h1>{{ project.name }}</h1>
  <h3>{{ project.client_name }}</h3>
  <p>{{ project.summary }}</p>
</template>



<style lang="scss" scoped>
h1 {
  color: black;
}
</style>
