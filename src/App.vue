<script>

import {store} from "../src/store";
import AppNav from "./components/AppNav.vue"
import AppGrid from "./components/AppGrid.vue"

export default{

  components:{
    AppNav,
    AppGrid,
  },

  data(){
    return{
      store,
    }
  },
  methods:{

    searchFilm(){
      // chiamata Api per i film
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=39fd68787b3ecc4c7f99e2428228f89c&language=en-US&query=${store.search}`).then((res)=>{
        console.log(res);

        store.films = res.data.results;

        console.log(store.films);
      });

      // chiamata API per le serie TV
      axios.get(`https://api.themoviedb.org/3/search/tv?api_key=39fd68787b3ecc4c7f99e2428228f89c&language=it_IT&query=${store.search}`).then((res)=>{
        console.log(res);

        store.serieTv = res.data.results;

        console.log(store.serieTv);
      });

      store.search='';
    }

  },
  mounted(){

    // axios.get(`https://api.themoviedb.org/3/tv/popular?api_key=39fd68787b3ecc4c7f99e2428228f89c?language=en-US&page=1`).then((res)=>{
    //     console.log(res);

    //     store.popular = res.data.results;

    //     console.log(store.popular);
    //   });

  }

}

</script>

<template>

  <AppNav @cercaFilm="searchFilm"></AppNav>

  <AppGrid></AppGrid>

</template>

<style lang="scss">

</style>
