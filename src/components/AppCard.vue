<template>
    <div class="container">
       
        <div class="title"> Title : {{ movie.title }} </div>
        <div class="image"> 
            <img :src="(`https://image.tmdb.org/t/p/w200${movie.poster_path}`)" alt="" srcset="">
        </div>

        <div class="original-title"> Original:  {{ movie.original_title }} </div>
        <div class="language"> 
            Language : {{ movie.original_language }} 
            <img v-if="languageHasImage()" :src= "require(`../assets/img/${movie.original_language}.png`)" alt="" srcset=""> 
         </div>
        <div class="vote"> Vote : {{ (parseInt(movie.vote_average / 2))}}
        <p>
            <i v-for="n in 5" :key="n" class="fa-star" :class="n <= (parseInt(movie.vote_average / 2)) ? 'fas' : 'far' "></i>
        </p> 
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

       starsCount(number) {
           if (number == 1) {
            this.stars = `<i class="far fa-star"></i>`
           }
       }
        
    }
}
</script>

<style lang="scss" scoped>
@import "./style/common.scss";

.container {
    border: 2px solid black;
    margin: 10px;
}

.image {
    width: 300px;
    height: 400px;
}

</style>