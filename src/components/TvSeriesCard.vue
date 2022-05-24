<template>
    <div class="container">
       
        <div class="title"> Title : {{ tvseries.name }} </div>
        <div class="original-title"> Original:  {{ tvseries.original_name }} </div>
        <div class="language"> 
            Language : {{ tvseries.original_language }} 
            <img v-if=" tvseries.original_language == 'en' || tvseries.original_language == 'it' " :src= "require(`../assets/img/${tvseries.original_language}.png`)" alt="" srcset=""> 
            <img v-else :src="image" alt="" srcset=""> 
         </div>
        <div class="vote"> Vote : {{ tvseries.vote_average }} </div>
        
      
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
        }
    },

    methods: {
       
        
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