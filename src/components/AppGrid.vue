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

    <h3>{{ store.choice }}</h3>
    <div v-if="store.choice == 'Film'" class="row">
      <AppFilmItem
          v-for="currentFilm in store.films"
          :imagePath=currentFilm.poster_path
          :title=currentFilm.title
          :originalTitle=currentFilm.original_title
          :lang=currentFilm.original_language
          :rating=currentFilm.vote_average
          :trama=currentFilm.overview
      >
      </AppFilmItem>

    </div>

    <div v-else-if="store.choice == 'Serie Tv'" class="row">
      <AppFilmItem
          v-for="currentSerie in store.serieTv"
          :imagePath=currentSerie.poster_path
          :title=currentSerie.name
          :originalTitle=currentSerie.original_name
          :lang=currentSerie.original_language
          :rating=currentSerie.vote_average
          :trama=currentSerie.overview
      >
      </AppFilmItem>
    </div>

   </div>

</template>

<style lang="scss">

#grid{
    padding:30px 10px;

    .row{
      display:flex;
      gap:10px;
      flex-wrap: wrap;
    }
}

</style>
