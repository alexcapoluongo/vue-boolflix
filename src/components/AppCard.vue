<template>
    <div class="container">
        <div class="image"> 
            <img :src=" movie.poster_path ? `https://image.tmdb.org/t/p/w200${movie.poster_path}` : require('../assets/img/no-image.jpeg')" alt="" srcset="">
        </div>

        <div class="wrap-title">
            <div class="title"> Title : {{ movie.title }} </div>

            <div class="original-title"> Original:  {{ movie.original_title }} </div>
            <div class="language"> 
                Language : {{ movie.original_language  }} 
                <img v-if="languageHasImage()" :src= "require(`../assets/img/${movie.original_language}.png`)" alt="" srcset=""> 
            </div>
            <div class="vote"> Vote : {{ (Math.ceil(movie.vote_average / 2))}}
            <p class="stars">
                <i v-for="n in 5" :key="n" class="fa-star" :class="n <= (parseInt(movie.vote_average / 2)) ? 'fas' : 'far' "></i>
            </p> 
            <p class="overview-movie">
                {{ movie.overview }}
            </p>
            </div>
        </div>
    </div>
</template>

<script>


export default {
    name: "AppCard",
    props: {
        movie: Object,
    },

    data() {
        return{
            flags: ['it', 'en', 'fr']
        }
    },

    methods: {

        languageHasImage() {
            return this.flags.includes(this.movie.original_language)
        },        

    }
}
</script>

<style lang="scss" scoped>
@import "./style/common.scss";

.container {
    height: 454px;
    width: 304px;
    border: 2px solid white;
    margin: 10px;
    color:white;
    text-align: center;
    position: relative;

    .wrap-title {
        display: none;
        position: absolute;
        z-index: 999;
        top: 0;
        left:0;
        width: 100%;
        height:100%;
    }

    .title {
        font-size: 1.5em;
        margin-bottom: 20px;
        margin-top: 20px;
    }

    .original-title {
        font-size: 1.2em;
        margin-bottom: 10px;
    }

    .language {
        margin-bottom: 10px;
    }

    .stars {
        color: rgb(255, 179, 0);
    }

    .overview-movie {
        margin-top: 20px;
    }
}

.container:hover .wrap-title{
    background-color: rgba(0, 0, 0, .7);
    display: inline-block;
}

.image {
    text-align: center;
    margin-bottom: 30px;

    img {
        width: 300px;
    }
}

</style>