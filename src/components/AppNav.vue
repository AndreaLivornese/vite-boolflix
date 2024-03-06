<script>

import {store} from "../store";

export default{
    name:"AppNav",

  data(){
    return{
      store,
    }
  }
}

</script>

<template>

    <nav>
        <div id="left">
            <div class="logo">
                <img src="" alt="logo">
            </div>
            <div class="links">
                <ul>
                    <li>Home</li>
                    <li>Film</li>
                    <li>Serie TV</li>
                </ul>
            </div>
        </div>

        <div id="right">
            <input type="search" v-model="store.search">
            <input type="button" value="cerca" @click="$emit('cercaFilm')">
        </div>


    </nav>

</template>

<style>

nav{
    display: flex;
    justify-content: space-between;

    padding:15px 30px;

    #left{
        display:flex;
        gap:40px;

        ul{
            list-style-type: none;
            display: flex;

            gap:15px;
        };
    }

}

</style>
