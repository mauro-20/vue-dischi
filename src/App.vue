<template>
  <div id="app">
    <Header :logo-src="require('./assets/images/spotify-logo.png')" @selectGenre="selectGenre"/>
    <Albums :genre="genre"/>
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
      genre: ''
    }
  },
  methods: {
    selectGenre(genre) {
      console.log(genre);
      this.genre = genre
    }
  }
}
</script>

<style lang="scss">
  @import './assets/style/common';


</style>
