<template>
  <header class="">
    <div class="my-container row justify-content-between align-items-center">
      <div class="col-10">
        <img src="../assets/img/logo.png" alt="logo"  />
      </div>
      <div class="col-2">
        
        <select class="form-select" v-model="currentGenre" >
          <option value="">Selziona tutti i generi</option>
          <option v-for="(genre,index) in genres" :key="index" :value="genre">{{genre}}</option>
        
         
        </select>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
  props:['genres'],
  data(){
      return{
          currentGenre:'',
      }
  }
};
</script>

<style lang="scss">
@import "../assets/scss/vars.scss";
header {
  height: 90px;
  width: 100%;
  background-color: $secondary-color;
  box-shadow:  0px  0px 10px rgba($green-spotify,0.4);

  position: fixed;
  top: 0;
  left: 0;

  .row {
    height: 100%;
    width: 100%;
  }
  img {
    max-width: 5%;
  }
}
</style>