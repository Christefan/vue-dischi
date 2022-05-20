<template>
  <main class="py-4">
    <RicercaAlbum @searchedClick="saveAlbum($event)" />
    <div class="container">
      <div class="row row-cols-5">
        <AlbumList
          v-for="(items, index) in filterGenreArr"
          :key="index"
          :album="items"
        />
      </div>
    </div>
  </main>
</template>
<script>
import AlbumList from "./AlbumList.vue";
import RicercaAlbum from "./RicercaAlbum.vue";
import axios from "axios";
export default {
  name: "AppMain",
  components: {
    AlbumList,
    RicercaAlbum,
  },
  data() {
    return {
      albums: [],
      search: "",
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((resp) => {
        this.albums = resp.data.response;
      });
  },
  computed: {
    filterGenreArr: function () {
      const filteredGenre = this.albums.filter((item) => {
        return item.genre.toLowerCase().includes(this.search);
      });
      return filteredGenre;
    },
  },
  methods: {
    saveAlbum: function (searchKey) {
      this.search = searchKey.toLowerCase();
    },
  },
};
</script>

<style scoped>
.main-container {
  height: 50vh;
  background-color: rgb(61, 58, 58);
}
</style>
