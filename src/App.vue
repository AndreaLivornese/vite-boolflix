<script>

import {store} from "../src/store";
import AppNav from "./components/AppNav.vue"

export default{

  components:{
    AppNav,
  },

  data(){
    return{
      store,
    }
  },
  methods:{

    searchFilm(){
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=39fd68787b3ecc4c7f99e2428228f89c&language=en-US&query=${store.search}`).then((res)=>{
        console.log(res);

        store.films = res.data.results;

        console.log(store.films);
      });

      store.search='';
    }

  }

}

</script>

<template>

  <AppNav @cercaFilm="searchFilm"></AppNav>

</template>

<style>

</style>
