<template>
  <div class="prova">
    <img :src="album.poster" />
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
