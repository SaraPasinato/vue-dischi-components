<template>
  <div class="card-albums text-light">
      <img :src="album.poster" :alt="album.title" class="w-100 pt-3">
      <div class="card-body">
          <p class="fs-6 card-title mb-0"> {{album.title}}</p>
          <p class="fw-lighter card-text">{{album.year}}</p>
      </div>
  </div>
</template>

<script>
export default {
    name:'CardAlbums',
    props:['album'],
}
</script>

<style lang="scss">
@import "../assets/scss/vars.scss";

.card-albums{
   background-color: $secondary-color;
    min-height: 300px;
    text-align: center;
    border-radius: 5px;
    box-shadow:  2px 2px 10px $dark-color; 

    img{
      max-width: 55%;
      height: auto;
    }

    .card-body{
        color:$gray-color;
        
    }
}

</style>