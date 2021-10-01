<template>
  <div id="app">
    <Header :logo-src="require('./assets/images/spotify-logo.png')"/>
    <Albums/>
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
  }
}
</script>

<style lang="scss">
  @import './assets/style/common';


</style>
