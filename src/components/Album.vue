<template>
  <div class="album">
    <div class="album-img">
      <img :src="info.poster" :alt="info.title">
    </div>
    <h3 class="album-title">{{info.title}}</h3>
    <div class="album-author">{{info.author}}</div>
    <div class="album-year">{{info.year}}</div>
  </div>
</template>

<script>
export default {
  name: 'Album',
  props: ['info']
}
</script>

<style lang="scss" scoped>
  @import '../assets/style/variables';

  .album{
    display: flex;
    flex-direction: column;
    align-items: center;
    width: calc(100% / 5 - 1.25rem);
    background-color: $headerBgColor;
    margin-bottom: 1.5625rem;
    padding: 1.5625rem;
    text-align: center;
    cursor: pointer;

    &-img{
      width: 100%;

      img{
        width: 100%;
      }
    }
    &-title{
      margin: 20px 0;
      text-transform: uppercase;
      color: $textLight;
    }
    &-author,
    &-year{
      color: $textDark;
    }

  }

</style>