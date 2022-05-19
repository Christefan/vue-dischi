<template>
  <div class="main-container">
    <AlbumList v-for="(items, index) in albums" :key="index" :album="items" />
  </div>
</template>
<script>
import AlbumList from "./AlbumList.vue";
import axios from "axios";
export default {
  name: "AppMain",
  components: {
    AlbumList,
  },
  data() {
    return {
      albums: [],
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((resp) => {
        this.albums = resp.data.response;
      });
  },
};
</script>

<style scoped>
.main-container {
  height: 50vh;
  background-color: rgb(61, 58, 58);
}

.prova {
  width: 40px;
  border: 1px solid blue;
}
</style>
