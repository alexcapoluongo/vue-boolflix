<template>
  <div>
        <AppCard 
        v-for="(element, index) in moviesArray"
        :key="index"
        :cardObj="element"
        />
        
  </div>
</template>

<script>

import axios from "axios";
import AppCard from "./AppCard.vue"

export default {
    name: "MovieList",

    components: {
        AppCard,
    },

    data: function () {
        return {
            moviesArray: [],
        }
    },

    created() {
        axios
            .get("https://api.themoviedb.org/3/movie/550?api_key=b6a9e07e1f27a49e3055f0942a745d07")
            .then((resp) => {
                this.moviesArray = resp.data;
            });
    }
}
</script>

<style>

</style>