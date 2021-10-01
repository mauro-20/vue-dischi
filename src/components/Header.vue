<template>
  <header>
    <div class="logo">
      <img :src="src" alt="Logo">
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: ['src']
}
</script>

<style lang="scss" scoped>
  @import '../assets/style/variables';
  .logo{
    background-color: $headerBgColor;
    padding: .625rem 1.25rem;

    img{
      width: 3.125rem;
    }
  }

</style>