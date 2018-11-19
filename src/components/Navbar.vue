<template>
  <div>
    <router-link :to="`/`">
      home
    </router-link>
    <router-link :to="`/movies`">
      movies
    </router-link>
  </div>
</template>

<script>
  export default {
    name: "Navbar"
  }
</script>

<style scoped>

</style>
