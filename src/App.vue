<template>
  <div id="app">
      <Header @doSearch="setSearch($event)" />
      <!-- :inputValue="Selection"  -->
      <Main :Movies="Selection" :baseLink="imgBase"/>
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
      Selection: {
        films:[],
        series:[],
      },
      imgBase: 'https://image.tmdb.org/t/p/w342',
    }
  },
  methods: {
    setSearch(value) {
      this.Selection.films = value.selectedMovies;
      this.Selection.series = value.selectedTv;
      console.log(value.selectedMovies);
    }
  },
};
</script>

<style lang="scss">
  @import "~bootstrap/scss/bootstrap";
  @import "~mdb-ui-kit/css/mdb.min.css";
  @import "./assets/scss/style.scss";

// /* #app {
//   font-family: Avenir, Helvetica, Arial, sans-serif;
//   -webkit-font-smoothing: antialiased;
//   -moz-osx-font-smoothing: grayscale;
//   text-align: center;
//   color: #2c3e50;
//   margin-top: 60px;
// } */
</style>
