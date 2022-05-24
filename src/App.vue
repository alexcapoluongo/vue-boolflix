<template>
  <div id="app">
    <AppHeader @searchClick= "search($event)"/>
    <main>
      <MovieList :movies="moviesList" />
    </main>
  </div>
</template>

<script>
import axios from "axios";
import MovieList from "./components/MovieList.vue";
import AppHeader from "./components/AppHeader.vue";

export default {
  name: 'App',
  
  data() {
    return {
      moviesList: []
    }
  },

  methods: {
    search(inputUser) {
      axios
          .get(`https://api.themoviedb.org/3/search/movie?api_key=b6a9e07e1f27a49e3055f0942a745d07&language=en-US&page=1&include_adult=false&query=` + inputUser)
          .then((resp) => {
              this.moviesList = resp.data.results;
          });

    }
  },

  components: {
    MovieList,
    AppHeader,
  }
}
</script>

<style lang="scss">

</style>
