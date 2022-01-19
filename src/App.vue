<template>
  <div id="app">
    <div class="container-fluid">
      <Header @doSearch="setSearch($event)" :inputValue="textValue" />
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
    Main,
    Header,
  },
  data() {
    return {
      textValue: '',
    }
  },
  methods: {
    setSearch(value) {
      this.textValue = value;
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
