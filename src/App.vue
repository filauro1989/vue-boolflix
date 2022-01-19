<template>
  <div id="app">
    <div class="container-fluid">
      <Header @doSearch="setSearch($event)" :inputValue="completedApi" />
      <Main />
    </div>
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import Main from "./components/Main.vue";
import Header from "./components/Header.vue";

export default {
  name: "App",
  components: {
    // HelloWorld,
    Header,
    Main,
  },
  data() {
    return {
      completedApi: '',
      staticApi: 'https://api.themoviedb.org/3/search/movie?api_key=f134f75db1d5edf07240f2412a109c60&query=',
    }
  },
  methods: {
    setSearch(value) {
      this.completedApi = this.staticApi + value;
    }
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap"
// /* #app {
//   font-family: Avenir, Helvetica, Arial, sans-serif;
//   -webkit-font-smoothing: antialiased;
//   -moz-osx-font-smoothing: grayscale;
//   text-align: center;
//   color: #2c3e50;
//   margin-top: 60px;
// } */
</style>
