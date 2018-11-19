<template>
    <div class="poster">
      <MovieImage v-bind:img-url="movie.thumb"
              v-bind:movie-ratings="movie.movieRatings" />
      <div class="name">{{movie.name}}</div>
      <div class="date">{{movie.releaseDate}}</div>
    </div>
</template>

<script>
    import MovieImage from '@/components/MovieImage.vue';
    export default {
      props: ['movie'],
      components: {
          MovieImage
      }
    }
</script>

<style scoped>
.poster {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 10px;
}
.name {
    font-size: 12px;
}
.date {
    font-size: 10px;
}
</style>