<script>

import {store} from "../src/store";
import AppNav from "./components/AppNav.vue"

export default{

  components:{
    AppNav
  },

  data(){
    return{
      store,
    }
  }
}

</script>

<template>

  <AppNav></AppNav>

</template>

<style>

</style>
