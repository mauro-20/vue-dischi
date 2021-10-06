<template>
  <header>
    <div class="logo">
      <img :src="logoSrc" alt="Logo">
    </div>
    <select name="genre" id="genre" v-model="genre" @change="$emit('selectGenre', genre)">
      <option value="">All</option>
      <option v-for="genre in genres" :key="genre" :value="genre">{{genre}}</option>
    </select>
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: ['logoSrc', 'genres'],
  data() {
    return {
      genre: ''
    }
  }
}
</script>

<style lang="scss" scoped>
  @import '../assets/style/variables';

  header{
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: $headerBgColor;
    padding: .625rem 1.25rem;
    
    .logo{
      width: 3.125rem;

      img{
        width: 100%;
      }
    }
  
    select{
      height: 1.5625rem;
      width: 6.25rem;
    }
  }


</style>