<template>
  <div id="app">
  <Header :genres="genres" @toParent="setcurrentGenre"/>
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
     currentGenre:'',
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
    filterGenres() {
      //recuperare i generi
      this.albums.forEach((el) => {
        if (!this.genres.includes(el.genre)) {
          this.genres.push(el.genre);
        }
      });
    },
   setcurrentGenre(str){
     this.currentGenre=str;
   }
  },
   created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.albums = res.data.response;
        this.filterByYear();
        this.filterGenres();
       
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
