<script>

import {store} from "../store";

export default{
    name:"AppNav",

  data(){
    return{
      store,
    }
  },
  methods:{

    choiceFilms(){
        store.choice = 'Film';
    },

    choiceSeries(){
        store.choice = 'Serie Tv';
    }

  }
}

</script>

<template>

    <nav>
        <div id="left">
            <div class="logo">
                <img src="https://image.tmdb.org/t/p/w92/wwemzKWzjKYJFfCeiB57q3r4Bcm.png" alt="logo">
            </div>
            <div class="links">
                <ul>
                    <li >Home</li>
                    <li @click="choiceFilms">Film</li>
                    <li @click="choiceSeries">Serie TV</li>
                </ul>
            </div>
        </div>

        <div id="right">
            <input type="search" v-model="store.search">
            <input type="button" value="cerca" @click="$emit('cercaFilm')">
        </div>


    </nav>

</template>

<style lang="scss">

nav{
    display: flex;
    justify-content: space-between;
    align-items: center;

    padding:15px 30px;

    #left{
        display:flex;
        gap:40px;

        ul{
            list-style-type: none;
            display: flex;

            gap:15px;

            li{
                user-select: none;
                cursor:pointer;
            }
        };
    }

}

</style>
