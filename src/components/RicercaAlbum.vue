<template>
  <div>
    <input type="text" placeholder="Scrivi" v-model="albumsearch" />
    <button @click="$emit('searchedClick', albumsearch)">Ricerca</button>
  </div>
</template>

<script>
export default {
  name: "RicercaAlbum",
  data: function () {
    return {
      albumsearch: "",
    };
  },
};
</script>

<style lang="less" scoped></style>
