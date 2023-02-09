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

    <div class="my-card-film" v-for="(film, index) in store.listFilm">
        <div v-if="film.poster_path == null" class="poster">
            <img src="../assets/image-not-found.jpg" alt="">
        </div>
        <div v-else class="poster">
            <img :src="`https://image.tmdb.org/t/p/w342${film.poster_path}`" :alt="film.title">
        </div>
        
        <div class="info-film">
            <h5 class="title">titolo:
                <p class="d-inline-block">{{ film.title }}</p>
            </h5>
            
            <h5 class="original-title">titolo originale:
                <p class="d-inline-block">{{ film.original_title }}</p>
            </h5>
            
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
    width: 100%;
}
.languages > img{
    width: 20px;
}
.yel{
    color: yellow;
}
</style>