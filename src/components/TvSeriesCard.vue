<template>
    <div class="container">
       
        <div class="image"> 
            <img :src="(`https://image.tmdb.org/t/p/w200${tvseries.poster_path}`)" alt="" srcset="">
        </div>

        <div class="wrap-title">
            <div class="title"> Title : {{ tvseries.name }} </div>
            <div class="original-title"> Original:  {{ tvseries.original_name }} </div>
            <div class="language"> 
                Language : {{ tvseries.original_language }} 
                <img v-if="languageHasImage()" :src= "require(`../assets/img/${tvseries.original_language}.png`)" alt="" srcset=""> 
            </div>
            <div class="vote"> Vote :  {{ this.stars }} {{ (parseInt(tvseries.vote_average / 2)) }} </div>
        </div>
      
    </div>
</template>

<script>

export default {
    name: "TvSeriesCard",
    props: {
        tvseries: Object,
    },

    data() {
        return{
            stars: "",
            flags: ['en', 'it', 'fr']
        }
    },

    methods: {

        languageHasImage() {
            return this.flags.includes(this.tvseries.original_language)
        },
    }
}
</script>

<style lang="scss" scoped>

.container {
    height: 454px;
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