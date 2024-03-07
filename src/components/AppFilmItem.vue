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
                <img :src="'https://image.tmdb.org/t/p/w300/' + imagePath">
            </div>

            <div class="title">
                {{title}}
            </div>
            <div class="original-title">
               {{originalTitle}}
            </div>
            <div class="lang">
                <img
                    :src="'https://flagcdn.com/w20/' + lang + '.png'"
                    width="20"
                    alt="bandiera">
            </div>
            <div class="rating">
                <i v-for="n in Math.floor(rating / 2 ) " class="fa-solid fa-star star"></i>
            </div>

        </div>

</template>

<style lang="scss">

.card{
    display: flex;
    flex-flow:row wrap;
    align-items: flex-end;

    padding:10px;

    width: calc(100% / 4 - 10px / 4 * 3);

    background-color: #0971e7;

    &>div{
        width: calc(100% / 2);

        .img img{
            width: 100%;
        }

    }
}

.star{
    color:yellow;
}


</style>
