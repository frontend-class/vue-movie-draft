<template>
  <div class="movie-view">
    <div>
      <h1>Movies</h1>

      <h2>현재상영작</h2>
      <div v-for="(movie, i) in releasedMovie"
          :key="i">
          <Poster v-bind:movie="movie" />
      </div>

      <h2>개봉예정작</h2>
      <div v-for="movie in upcomingMovie"
          :key="movie.id">
          <Poster v-bind:movie="movie" />
      </div>
    </div>

    <div v-if="open">
      상세화면
    </div>
  </div>
</template>

<script>
  import Poster from '@/components/Poster.vue';

  export default {
    name: "Movie",
    components: {
      Poster 
    },
    data() {
      return {
        open: false,
        movies: [
          {
            id: 1,
            thumb: 'https://movie-phinf.pstatic.net/20181029_21/1540774701820gU85o_JPEG/movie_image.jpg',
            name: '신비한 동물들과 그린델왈드의 범죄',
            movieRatings: '12',
            genre: '모험, 가족, 판타지',
            releaseDate: '2018.11.14',
            gradePoint: 7.83,
            director: "데이빗 예이츠",
            actors: "에디 레드메인, 조니 뎁",
          },
          {
            id: 2,
            thumb: 'https://movie-phinf.pstatic.net/20181031_68/1540952503496fNRsF_JPEG/movie_image.jpg',
            name: '보헤미안 랩소디',
            movieRatings: '12',
            genre: '드라마,',
            releaseDate: '2018.10.31',
            gradePoint: 9.52,
            director: "브라이언 싱어",
            actors: "라미 말렉, 루시 보인턴, 귈림",
          },
          {
            id: 3,
            thumb: 'https://movie-phinf.pstatic.net/20181106_289/1541478936071tmadh_JPEG/movie_image.jpg',
            name: '완벽한 타인',
            movieRatings: '15',
            genre: '드라마, 코미디',
            releaseDate: '2018.10.31',
            gradePoint: 9.14,
            director: "이재규",
            actors: "유해진, 조진웅, 이서진",
          },
          {
            id: 4,
            thumb: 'https://movie-phinf.pstatic.net/20181023_49/1540269777397VIFnu_JPEG/movie_image.jpg',
            name: '로빈슨의 언더워터 어드벤처',
            movieRatings: 'all',
            genre: '애니메이션',
            releaseDate: '2018.11.15',
            gradePoint: 7.25,
            director: "비탈리 무카메지아노브, 막심 볼코브",
            actors: "",
          },
          {
            id: 5,
            thumb: 'https://movie-phinf.pstatic.net/20181119_157/15425904764434IQke_JPEG/movie_image.jpg',
            name: '아쿠아맨',
            movieRatings: '15',
            genre: '액션, 모험, SF',
            releaseDate: '2018.12.19',
            gradePoint: 0,
            director: "제임스 완",
            actors: "제이슨 모모아, 엠버 허드, 니콜 키드먼, 패트릭 윌슨, 윌렘 대포, 돌프 룬드그렌",
          },
          {
            id: 6,
            thumb: '',
            name: '토이 스토리 4',
            movieRatings: 'all',
            genre: '애니메이션, 모험, 코미디, 가족, 판타지',
            releaseDate: '2019.06.01',
            gradePoint: 0,
            director: "조시 쿨리",
            actors: "톰 행크스, 팀 알렌, 조안 쿠삭, 애니 파츠, 패트리샤 아퀘트",
          },
        ]
      }
    },
    computed: {
      releasedMovie: function() {
        return this.movies.filter( m => m.releaseDate <= '2018.11.19');
      },
      upcomingMovie: function() {
        return this.movies.filter( m => m.releaseDate > '2018.11.19');
      }
    }
  }
</script>

<style scoped>
.movie-view {
  display: flex;
  justify-content: center;
}
</style>
