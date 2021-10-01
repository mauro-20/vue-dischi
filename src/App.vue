<template>
  <div id="app">
    <Header :src="require('./assets/images/spotify-logo.png')"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'

export default {
  name: 'App',
  components: {
    Header
  }
}
</script>

<style lang="scss">
  @import './assets/style/common';

</style>
