<template>
  <div id="app">
    <Header @searchInput="search" />
    <Main :moviesList="moviesArray"/>
  </div>
</template>

<script>
import axios from 'axios';
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";

export default {
  name: "App",
  components: {
    Header,
    Main,
  },
  data: function() {
    return {
      // API necessary
      searchMoviesString: '',
      apiKey: '1584bfdd76106d8fa0cd13aed08a65ef',
      // API Returns
      moviesArray: [],
    };
  },
  methods: {
    // Chiamata Movies
    searchMovies: function(){
      axios.get(
        'https://api.themoviedb.org/3/search/movie',
        {
          params: {
            api_key: this.apiKey,
            query: this.searchMoviesString,
          }
        }
      ).then((response) => {
        this.moviesArray = response.data.results;
      });
    },
    // Chiamata generale
    search: function(inputString){
      this.searchMoviesString = inputString;
      this.searchMovies();
    },
  }
};
</script>

<style lang="scss">

</style>
