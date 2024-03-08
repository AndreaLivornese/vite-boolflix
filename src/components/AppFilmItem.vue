<script>

export default{
    name:"AppFilmItem",

   props:{
    currentSearch: Object,
    imagePath:String,
    title:String,
    originalTitle:String,
    lang:String,
    rating:Number,
    trama:String,
   },
    
  data(){
    
    return{

    }
  },
}

</script>

<template>

        <div class="card">

            <div class="img">
                <img :src="'https://image.tmdb.org/t/p/w342/' + imagePath">
            </div>

            <div class="info">
                <div class="title">
                    <strong>Titolo: </strong>{{title}}
                </div>
                <div class="original-title">
                   <strong>Titolo originale: </strong>{{originalTitle}}
                </div>
                <div class="lang">
                   <strong>Nazionalità: </strong> 
                   <img
                        :src="'https://flagcdn.com/w20/' + lang + '.png'"
                        width="20"
                        alt="bandiera"
                    >
                </div>
                <div class="rating">
                   <strong>Voto: </strong> <i v-for="n in Math.floor(rating / 2 ) " class="fa-solid fa-star star"></i>
                </div>
                <div class="trama">
                    <strong>Trama:</strong>
                    {{ trama }}
                </div>
            </div>


        </div>

</template>

<style lang="scss">

.card{
    position:relative;

    width: calc(100% / 4 - 10px / 4 * 3);

    transition: 1s ;

    &:hover .info{
        z-index: 1;
        border:1px white solid;
    }

    .img{
        width: 100%;

        img{
            display: block;
            width: 100%;
        }
    } 
    

    .info{
        position: absolute;
        left:0;
        top:0;
        z-index: -1;

        padding:10px;

        width: 100%;
        height: 100%;
        overflow-y: auto;

        background-color: black;

        display: flex;
        flex-flow:column;
    }

   
}

.star{
    color:yellow;
}


</style>
