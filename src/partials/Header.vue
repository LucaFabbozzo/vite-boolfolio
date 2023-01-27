<script>
export default {
  name: 'Header',
}
</script>

<template>
  <header>
    <ul>
      <li><router-link :to="{ name: 'home' }">home</router-link></li>
      <li><router-link :to="{ name: 'projects' }">projects</router-link></li>
      <li><router-link :to="{ name: 'about' }">about</router-link></li>
      <li><router-link :to="{ name: 'contacts' }">contacts</router-link></li>
    </ul>
  </header>

</template>


<style lang="scss" scoped>
header {
  ul {
    text-align: center;

    li {
      display: inline-block;
      text-transform: uppercase;
      padding: 30px;
      font-size: 1.2rem;

      a {
        text-decoration: none;
        color: #393939;
      }
    }
  }
}
</style>
