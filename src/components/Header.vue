<template>
  <header>
    <div class="logo">
      <img :src="logoSrc" alt="Logo">
    </div>
    <select name="genre" id="genre" v-model="genre" @change="$emit('selectGenre', genre)">
      <option value="rock">rock</option>
      <option value="pop">pop</option>
      <option value="jazz">jazz</option>
      <option value="metal">metal</option>
    </select>
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: ['logoSrc'],
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