<template>
  <div id="app">
  <Header />
  <main>
    <Gallery/>
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
      selectFilterd:'',
    }
  },
  components: {
   Header,
   Gallery,
  }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap.scss";
@import "assets/scss/style.scss";

</style>
