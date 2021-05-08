<template>
  <div id="app">
    <MoviesList :list="moviesList" />
  </div>
</template>

<script>
import { mapActions, mapGetters } from "vuex";
import MoviesList from "./components/MoviesList.vue";

export default {
  name: "app",
  components: {
    MoviesList,
  },
  computed: {
    ...mapGetters("movies", ["moviesList"]),
  },
  methods: {
    ...mapActions("movies", ["fetchMovies"]),
  },
};
</script>

<style>
#app {
  font-family: "Arial", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
