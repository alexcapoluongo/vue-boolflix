<template>
    <div class="container">
       
        <div class="title"> Title : {{ movie.title }} </div>
        <div class="original-title"> Original:  {{ movie.original_title }} </div>
        <div class="language"> 
            Language : {{ movie.original_language }} 
            <img v-if=" movie.original_language == 'en' || movie.original_language == 'it' " :src= "require(`../assets/img/${movie.original_language}.png`)" alt="" srcset=""> 
            <img v-else :src="image" alt="" srcset=""> 
         </div>
        <div class="vote"> Vote : {{ movie.vote_average }} </div>
        
      
    </div>
</template>

<script>
import otherLanguage from "../assets/img/zz.png"

export default {
    name: "AppCard",
    props: {
        movie: Object,
    },

    data() {
        return{
            image: otherLanguage,
        }
    },

    methods: {
        // differentLanguage: function() {
        //     if ( this.movie.original_language !== "en" || this.movie.original_language !== "it" ) {
        //        this.visible = false }
        // }
        
    }
}
</script>

<style lang="scss" scoped>

.container {
    border: 2px solid black;
    width: 100px;
    margin: 10px
}


</style>