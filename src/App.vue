<template>
  <div id="app">
    <AppHeader @searchClick= "search($event)"/>
    <main>
      <h1>Movies</h1>
      <MovieList :movies="moviesList" />
      <h1>Tv Series</h1>
      <TvSeries :tvseries="tvSeriesList" />

    </main>
  </div>
</template>

<script>
import axios from "axios";
import MovieList from "./components/MovieList.vue";
import AppHeader from "./components/AppHeader.vue";
import TvSeries from "./components/TvSeries.vue";

export default {
  name: 'App',
  
  data() {
    return {
      moviesList: [],
      tvSeriesList: []
    }
  },

  methods: {
    search(inputUser) {
      axios
          .get(`https://api.themoviedb.org/3/search/movie?api_key=b6a9e07e1f27a49e3055f0942a745d07&language=en-US&page=1&include_adult=false&query=` + inputUser)
          .then((resp) => {
              this.moviesList = resp.data.results;
          });
      
      axios 
        .get(`https://api.themoviedb.org/3/search/tv?api_key=e99307154c6dfb0b4750f6603256716d&language=it_IT&query=` + inputUser)
        .then((resp) => {
          this.tvSeriesList = resp.data.results;
        });
    }
  },

  components: {
    MovieList,
    AppHeader,
    TvSeries
  }
}
</script>

<style lang="scss">

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;

} 

body {
  background-color: #1E1E24;
}

h1 {
  color: white;
  margin: 30px;
}

</style>
