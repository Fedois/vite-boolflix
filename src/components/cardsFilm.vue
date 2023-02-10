<script>
import {store} from '../store.js'
export default {
    name: 'cardsFilm',
    props: {
        type: Object
    },
    data (){
        return{
            store
        }
    },
    methods: {
        starsVote(vote){
            let numVote = vote;
            numVote = numVote / 2
            numVote = Math.ceil(numVote)
            console.log(numVote)
            return numVote
        }
    }
}
</script>

<template>
    <!-- FILM -->

    <div class="my-card mb-4 p-2" v-for="(film, index) in store.listFilm">
        <div class="my-box h-100 w-100 position-relative">
            <div v-if="film.poster_path == null" class="poster h-100">
                <img class="d-block w-100 h-100" src="../assets/image-not-found.jpg" :alt="film.title">
            </div>
            <div v-else class="poster h-100">
                <img class="d-block w-100 h-100" :src="`https://image.tmdb.org/t/p/w342${film.poster_path}`" :alt="film.title">
            </div>
            
            <div class="info-card p-2 h-100 w-100 position-absolute top-0 start-0 d-none">
                <h5 class="title mb-0">Titolo:</h5>
                <p class="d-inline-block">{{ film.title }}</p>
                
                <h5 class="original-title mb-0">Titolo originale:</h5>
                <p class="d-inline-block">{{ film.original_title }}</p>

                <h5 class="overview mb-0">Descrizione:</h5>
                <p>{{ film.overview }}</p>
                
                <h5 class="languages">Lingua:
                    <img :src="`/src/assets/Flag_${film.original_language}.svg.png`" :alt="film.original_language">
                </h5>
                
                <h5 class="vote">Voto:
                    <span class="yel" v-for="star in starsVote(film.vote_average)">&#9733;</span>
                    <span v-for="star in 5- starsVote(film.vote_average)">&#9734;</span>
                </h5>
            </div>
        </div>
    </div>

</template>

<style lang="scss" scoped>
@use '../partials/styleAllCards.scss' as *
</style>