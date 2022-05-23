<template>
  <div id="app">
    <AppHeader />
    <main>
      <MovieList />
    </main>
  </div>
</template>

<script>
import MovieList from "./components/MovieList.vue";
import AppHeader from "./components/AppHeader.vue";

export default {
  name: 'App',
  components: {
    MovieList,
    AppHeader,
  }
}
</script>

<style lang="scss">

</style>
