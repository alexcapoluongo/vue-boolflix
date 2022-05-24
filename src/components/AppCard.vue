<template>
    <div class="container">
       
        <div class="title"> Title : {{ movie.title }} </div>
        <div class="original-title"> Original:  {{ movie.original_title }} </div>
        <div class="language"> 
            Language : {{ movie.original_language }} <img :src="image" alt="" srcset="">
         </div>
        <div class="vote"> Vote : {{ movie.vote_average }} </div>
        
      
    </div>
</template>

<script>
import imageEn from "../assets/img/en.png"
import imageFr from "../assets/img/fr.png"
import imageIt from "../assets/img/it.png"
import imageWr from "../assets/img/zz.png"

export default {
    name: "AppCard",
    props: {
        movie: Object
    },

    data() {
        return{
            nameLanguage: "",
            image: imageEn
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