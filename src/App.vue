<template>
  <div id="app">
  <Header :genres="genres"/>
  <main>
    <Gallery :albums="albums"/>
  </main>
  </div>
</template>

<script>
   import axios from "axios";

  import Header from './components/Header.vue';
  import Gallery from './components/Gallery.vue';
export default {
  name: 'App',
  data(){
    return{
     albums: [],
     genres:[],
    }
  },
  components: {
   Header,
   Gallery,
  },
  methods:{
     filterByYear() {
      return this.albums.sort((a, b) => parseInt(a.year) - parseInt(b.year));
    },
    filterAlbums() {
      //recuperare i generi
      this.albums.forEach((el) => {
        if (!this.genres.includes(el.genre)) {
          this.genres.push(el.genre);
        }
      });
    },
  },
   created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.albums = res.data.response;
        this.filterByYear();
        this.filterAlbums();
       
      })
      .catch((e) => {
        console.error(e);
      });
  },
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";
@import "assets/scss/style.scss";

</style>
