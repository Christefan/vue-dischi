<template>
  <div>
    <label>Genere</label>
    <select v-model="albumsearch" @change="$emit('searchedClick', albumsearch)">
      <option value="">All</option>
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="jazz">Jazz</option>
      <option value="metal">Metal</option>
    </select>
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
