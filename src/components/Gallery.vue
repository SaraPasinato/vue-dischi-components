<template>
  <section id="gallery" class="container-sm">
      <div class="row align-items-center justify-content-center pt-2 g-5">
          <div class="col-12 col-sm-6 col-md-4 col-lg-3 " v-for="album in albums" :key="album.id">
          <CardAlbums :album="album"/>
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
    }
 },
 components:{
     CardAlbums,
 },
 created(){
     axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((res)=>{
         this.albums=res.data.response;
     }).catch((e)=>{
         console.error(e);
     });
 },
}
</script>

<style lang="scss">
#gallery{
   margin-top:60px;
   margin-bottom:60px;
    .row{
        height: 100%;   
    }
}
</style>