<template>
    <div class="movie-image">
        <img v-if="imgUrl !== ''" v-bind:src="imgUrl" width="100" height="100"/>
        <img v-else src="../assets/noimage.jpg" width="100" height="100"/>
        <div class="ratings"
             v-bind:style="{ background: ratingColor}"
        >
            {{movieRatings}}
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            imgUrl: {
                type: String,
                default: '',
            },
            movieRatings: {
                type: String,
                default: '전체',
            }
        },
        computed: {
            ratingColor: function() {
                if(this.movieRatings === '12') {
                    return 'blue';
                }
                else if(this.movieRatings === '15') {
                    return 'orange';
                }
                else {
                    return 'green';
                }
            }
        }
    }
</script>

<style scoped>
.movie-image {
    position: relative;
    width: fit-content;
}
.ratings {
    position: absolute;
    top: 5px;
    left: 5px;
    background: white;
    border-radius: 25px;
    font-size: 12px;
    padding: 3px;
    color: white;
}
</style>