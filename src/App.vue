<template>
  <div id="app">
    <Header :logo-src="require('./assets/images/spotify-logo.png')" :genres="genres" @selectGenre="selectGenre"/>
    <Albums @genreList="genreList" :genre="selectedGenre"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Albums from './components/Albums.vue'

export default {
  name: 'App',
  components: {
    Header,
    Albums
  },
  data() {
    return {
      genres: [],
      selectedGenre: ''
    }
  },
  methods: {
    selectGenre(genre) {
      console.log(genre);
      this.selectedGenre = genre
    },
    genreList(list){
      this.genres = list
    }
  }
}
</script>

<style lang="scss">
  @import './assets/style/common';


</style>
