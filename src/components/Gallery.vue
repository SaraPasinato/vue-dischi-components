<template>
  <section id="gallery" class="container-sm">
    <div class="row align-items-center justify-content-center pt-2 g-5">
      <div
        class="col-12 col-sm-6 col-md-4 col-lg-3"
        v-for="album in albums"
        :key="album.id"
      >
        <CardAlbums :album="album" />
      </div>
    </div>
  </section>
</template>

<script>
import axios from 'axios';
import CardAlbums from './CardAlbums.vue';
export default {
 name:'Gallery',
 data(){
    return{
        albums:[],
        genres: [],
    }
 },
 components:{
     CardAlbums,
 },
 methods:{
      filterByYear() {
      return (this.albums.sort((a, b) => parseInt(a.year) - parseInt(b.year)));
    },
    filterAlbums() {
      //recuperare i generi
      this.albums.forEach(el => {
        if(!this.genres.includes(el.genre)){
          this.genres.push(el.genre);
        }
      });
 }
 },
 created(){
     axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((res)=>{
         this.albums=res.data.response;
         this.filterByYear();
         this.filterAlbums();
         
     }).catch((e)=>{
         console.error(e);
     });
 },
 
}
</script>

<style lang="scss">
#gallery {
  margin-top: 60px;
  margin-bottom: 60px;
  .row {
    height: 100%;
  }
}
</style>