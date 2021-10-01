<template>
  <section class="albums">
    <div class="container">
      <Album v-for="(album, index) in albums" :key="index" :info= "album"/>
    </div>
  </section>
</template>

<script>
import Album from './Album.vue'
import axios from 'axios'

export default {
  name: 'Albums',
  components: {
    Album
  },
  data() {
    return {
      albums: []
    }
  },
  created() {
    axios
      .get('https://flynn.boolean.careers/exercises/api/array/music')
      .then( (res) => {
        this.albums = res.data.response;
      })
  }
}
</script>

<style lang="scss" scoped>
  @import '../assets/style/variables';

  .albums{
    background-color: $bgColor;
    overflow: auto;
  }
  .container{
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-content: flex-start;
    max-width: $sizeContainer;
    margin: 0 auto;
    padding: 6.25rem;
  }

</style>