<script>

export default{
    name:"AppFilmItem",

   props:{
    title:String,
    originalTitle:String,
    lang:String,
    rating:Number,
   },
    
  data(){
    
    return{

    }
  }
}

</script>

<template>

        <div class="card">

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
                {{ rating }}
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
    }
}


</style>
