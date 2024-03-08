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

    
    <div v-if="store.choice == ''" class="home">
      
      Comincia la tua ricerca per il tuo film o la tua serie tv. Inserisci qualche parola chiave sopra, clicca sulla categoria ed inizia la tua esplorazione tra centinaia di flim e serie tv.
      
    </div>
    
    <div v-else-if="store.choice == 'Home'" class="row">
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

    <div v-else-if="store.choice == 'Film'" class="row">
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
    height: calc(100vh - 61px);
    overflow-y: auto;

    .row{
      display:flex;
      gap:10px;
      flex-wrap: wrap;
    }

    .home{
      display: flex;
      justify-content: center;
      align-items: center;

      width: 100%;
      height: 100%;

      color:red;

      text-align: center;
      font-weight: bold;
      font-size: 24px;
    }
}

</style>
