<script>

import {store} from "../store";
import AppFilmItem from "./AppFilmItem.vue";

export default{
    name:"AppGrid",

  components:{
    AppFilmItem,
  },

  data(){
    return{
      store,
    }
  }
}

</script>

<template>

   <div id="grid">

    <AppFilmItem
        v-for="currentFilm in store.films"
        :title="currentFilm.title"
        :originalTitle="currentFilm.original_title"
        :lang="currentFilm.original_language"
        :rating="currentFilm.vote_average"
    >
    </AppFilmItem>

   </div>

</template>

<style lang="scss">

#grid{
    display:flex;
    gap:10px;
    flex-wrap: wrap;
}

</style>
