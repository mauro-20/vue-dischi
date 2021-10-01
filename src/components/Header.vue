<template>
  <header>
    <div class="logo">
      <img :src="logoSrc" alt="Logo">
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: ['logoSrc']
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