<script>
export default {
  name: 'ProjectItem',
  props: {
    project: Object
  },
  data() {
    return {

    }
  },

}
</script>

<template>
  <div class="projects-box">
    <!-- <div>
      <img :src="project.cover_image" :alt="project.name">
    </div> -->
    <h3>
      <router-link :to="{ name: 'detail', params: { slug: project.slug } }">{{ project.name }}</router-link>
    </h3>
    <p>{{ project.summary }}</p>
  </div>
</template>


<style lang="scss" scoped>
.projects-box {
   padding-bottom: 20px;

   h3 {
     padding-bottom: 10px;

     a {
       color: black;
     }

     p {
       padding-bottom: 10px;
     }
   }
 }
</style>
