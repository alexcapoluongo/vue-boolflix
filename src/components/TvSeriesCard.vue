<template>
    <div class="container">
       
        <div class="title"> Title : {{ tvseries.name }} </div>
        <div class="image"> 
            <img :src="(`https://image.tmdb.org/t/p/w200${tvseries.poster_path}`)" alt="" srcset="">
        </div>
        <div class="original-title"> Original:  {{ tvseries.original_name }} </div>
        <div class="language"> 
            Language : {{ tvseries.original_language }} 
            <img v-if=" tvseries.original_language == 'en' || tvseries.original_language == 'it' " :src= "require(`../assets/img/${tvseries.original_language}.png`)" alt="" srcset=""> 
            <img v-else :src="image" alt="" srcset=""> 
         </div>
        <div class="vote"> Vote : &#9733; {{ this.starsCount((parseInt(movie.vote_average / 2))) }} {{ this.stars }} {{ (parseInt(movie.vote_average / 2)) }} </div>
        
      
    </div>
</template>

<script>
import otherLanguage from "../assets/img/zz.png"

export default {
    name: "TvSeriesCard",
    props: {
        tvseries: Object,
    },

    data() {
        return{
            image: otherLanguage,
            stars: ""
        }
    },

    methods: {
       starsCount(number) {
           if (number == 1)
            number = "&#9733;"
       }
        
    }
}
</script>

<style lang="scss" scoped>

.container {
    border: 2px solid black;
    margin: 10px;

}

.image {
    width: 300px;
    height: 400px;
}


</style>