
<script>
import axios from 'axios'
export default {
  name: 'App',
data() {
  return {
    baseUrl: 'http://127.0.0.1:8000/api/'
  }
  },
  methods: {
    getApi() {
      axios.get(this.baseUrl + 'projects')
        .then(result => {
          console.log(result.data)
        })
    }
  },
  mounted() {
    this.getApi();
  }
}
</script>

<template>
  <h1>Ciao</h1>
</template>


<style lang="scss">
@use './style/general';

</style>