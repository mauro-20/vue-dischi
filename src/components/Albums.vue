<template>
  <section class="albums">
    <div class="container">
      <Album
        v-for="(album, index) in filterByGenre"
        :key="index"
        :info="album"
      />
    </div>
  </section>
</template>

<script>
import Album from "./Album.vue";
import axios from "axios";

export default {
  name: "Albums",
  props: {
    genre: String,
  },
  components: {
    Album,
  },
  data() {
    return {
      albums: [],
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.albums = res.data.response;
        const genreList = [];
        this.albums.forEach((album) => {
          if (!genreList.includes(album.genre)) {
            genreList.push(album.genre);
          }
        });
        this.$emit("genreList", genreList);
      });
  },
  computed: {
    filterByGenre() {
      return this.albums.filter((album) => {
        return (
          album.genre == this.genre||
          this.genre == ""
        );
      });
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/style/variables";

.albums {
  background-color: $bgColor;
  overflow: auto;
}
.container {
  display: flex;
  flex-wrap: wrap;
  align-content: flex-start;
  max-width: $sizeContainer;
  margin: 0 auto;
  padding: 6.25rem;
}
</style>