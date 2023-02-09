<script>
import {store} from '../store.js'
export default {
    name: 'cardsFilm',
    data (){
        return{
            store
        }
    }
}
</script>

<template>
    <!-- FILM -->

    <div class="my-card-film mb-4 p-2 position-relative" v-for="(film, index) in store.listFilm">
        <div v-if="film.poster_path == null" class="poster h-100">
            <img class="d-block w-100 h-100" src="../assets/image-not-found.jpg" :alt="film.title">
        </div>
        <div v-else class="poster h-100">
            <img class="d-block w-100 h-100" :src="`https://image.tmdb.org/t/p/w342${film.poster_path}`" :alt="film.title">
        </div>
        
        <div class="info-film p-2 h-100 w-100 position-absolute top-0 start-0 d-none">
            <h5 class="title mb-0">titolo:</h5>
            <p class="d-inline-block">{{ film.title }}</p>
            
            <h5 class="original-title mb-0">titolo originale:</h5>
            <p class="d-inline-block">{{ film.original_title }}</p>

            <h5 class="overview mb-0">descrizione:</h5>
            <p>{{ film.overview }}</p>
            
            <h5 class="languages">lingua:
                <img :src="`/src/assets/Flag_${film.original_language}.svg.png`" :alt="film.original_language">
            </h5>
            
            <h5 class="vote">voto:
                <span :class="{'yel' : film.vote_average >= 0}">&#9733;</span>
                <span :class="{'yel' : film.vote_average > 1}">&#9733;</span>
                <span :class="{'yel' : film.vote_average > 2}">&#9733;</span>
                <span :class="{'yel' : film.vote_average > 3}">&#9733;</span>
                <span :class="{'yel' : film.vote_average > 4}">&#9733;</span>
            </h5>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    .poster > img{
        object-fit: cover;
    }
    .info-film{
        background-color: rgba($color: #000000, $alpha: 0.8);
        overflow: auto;
        .languages > img{
            width: 20px;
            }
        .yel{
            color: yellow;
        }
    }
.my-card-film:hover{
    cursor: pointer;

    & .info-film{
        display: block !important;
    }
}
::-webkit-scrollbar {
  width: 5px;
}
::-webkit-scrollbar-thumb {
  background: #e1e1e1;
  border: 20px none #ffffff;
  border-radius: 50px;
}
::-webkit-scrollbar-thumb:hover {
  background: blue;
}
::-webkit-scrollbar-thumb:active {
  background: #e1e1e1;
}
</style>