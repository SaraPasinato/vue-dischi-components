<template>
  <section id="gallery" class="container-sm">
    <div class="row align-items-center justify-content-center pt-2 g-5">
      <div
        class="col-12 col-sm-6 col-md-4 col-lg-3"
        v-for="album in albums"
        :key="album.id" >
        <CardAlbums :album="album" />
      </div>
    </div>
  </section>
</template>

<script>
import CardAlbums from "./CardAlbums.vue";
export default {
  name: "Gallery",
  props:['albums'],
  data() {
    return {
     
    };
  },
  components: {
    CardAlbums,
  },
  methods: {
   
  },
 
};
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