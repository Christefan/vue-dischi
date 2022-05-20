<template>
  <div class="prova">
    <div class="img_prova">
      <img :src="album.poster" />
    </div>
    <h3>{{ album.title }}</h3>
    <p>{{ album.author }}</p>
    <p>{{ album.year }}</p>
  </div>
</template>
<script>
export default {
  name: "AlbumList",
  props: {
    album: Object,
  },
};
</script>
<style scoped lang="scss">
.prova {
  padding: 1rem;
  margin: 0.1rem;
  text-align: center;
  height: 400px;
  background-color: #2e3a46;

  h3 {
    color: white;
  }
  p {
    margin: -0.3rem;
    color: rgb(186, 175, 175);
  }
  img {
    width: 100%;
  }
}
</style>
