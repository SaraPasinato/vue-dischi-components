<template>
  <div id="app">
  <Header />
  <main>
    <Gallery @:childToParent="getGenreFromChild"/>
  </main>
  </div>
</template>

<script>
  import Header from './components/Header.vue';
  import Gallery from './components/Gallery.vue';
export default {
  name: 'App',
  data(){
    return{
     genres:[],
    }
  },
  components: {
   Header,
   Gallery,
  },
  methods:{
    getGenreFromChild(arr){
      this.genres=arr;
    }
  },
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";
@import "assets/scss/style.scss";

</style>
