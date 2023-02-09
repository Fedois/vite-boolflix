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
            
            <h5 v-if="film.original_language == 'en'" class="languages">lingua:
                <img src="../assets/Flag_en.svg.png" :alt="film.original_language">
            </h5>
            <h5 v-else-if="film.original_language == 'it'" class="languages">lingua:
                <img src="../assets/Flag_it.svg.png" :alt="film.original_language">
            </h5>
            <h5 v-else-if="film.original_language == 'fr'" class="languages">lingua:
                <img src="../assets/Flag_fr.svg.jpg" :alt="film.original_language">
            </h5>
            <h5 v-else class="languages">lingua:
                <p class="d-inline-block">{{ film.original_language }}</p>
            </h5>
            
            <h5 class="vote">voto:
                <p class="d-inline-block">{{ film.vote_average }}</p>
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
</style>