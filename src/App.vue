<template>
  <div id="app">
    <app-search v-on:queryRequested="handleSearchRequest($event)"></app-search>
    <app-preview :gifts="gifts"></app-preview>
  </div>
</template>

<script>
import Search from "./components/Search.vue";
import Preview from "./components/Preview.vue";
export default {

  name: "app",
  data() {
    return {
      msg: "Welcome to Your Vue.js App",
      gifts: []
    };
  },
  components: {
    appSearch: Search,
    appPreview: Preview,
  },

  methods: {
    doQuery:function(url) {
      fetch(url)
        .then(res => {
          return res.json();
        })
        .then(res => {
          this.gifts = res.data;
        });
    },
    handleSearchRequest(query) {
      const url =
        "http://api.giphy.com/v1/gifs/search?q=" +
        query +
        "&api_key=TijNEHa2lSPDyZg4M461SOSFiuuyRagg";
      this.doQuery(url);
    }
  },
  created() {
      const url =
      "http://api.giphy.com/v1/gifs/trending?api_key=TijNEHa2lSPDyZg4M461SOSFiuuyRagg";
      this.doQuery(url)
  }

  
  
};
</script>




<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
