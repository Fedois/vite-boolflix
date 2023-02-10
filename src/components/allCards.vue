<script>
import {store} from '../store.js'
export default {
    name: 'cardstype',
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

            if(numVote == 0){
                numVote = 1
            }
            
            return numVote
        }
    }
}
</script>

<template>
    <!-- FILM -->

    <div class="my-card mb-4 p-2">
        <div class="my-box h-100 w-100 position-relative">
            <div v-if="type.poster_path == null" class="poster h-100">
                <img class="d-block w-100 h-100" src="../assets/image-not-found.jpg" :alt="type.title">
            </div>
            <div v-else class="poster h-100">
                <img class="d-block w-100 h-100" :src="`https://image.tmdb.org/t/p/w342${type.poster_path}`" :alt="type.title">
            </div>
            
            <div class="info-card p-2 h-100 w-100 position-absolute top-0 start-0 d-none">
                <h5 class="title mb-0">Titolo:</h5>
                <p class="d-inline-block">{{ type.title }}</p>
                
                <h5 class="original-title mb-0">Titolo originale:</h5>
                <p class="d-inline-block">{{ type.original_title }}</p>

                <h5 class="overview mb-0">Descrizione:</h5>
                <p>{{ type.overview }}</p>
                
                <h5 class="languages">Lingua:
                    <img :src="`/src/assets/Flag_${type.original_language}.svg.png`" :alt="type.original_language">
                </h5>
                
                <h5 class="vote">Voto:
                    <span class="yel" v-for="star in starsVote(type.vote_average)">&#9733;</span>
                    <span v-for="star in 5 - starsVote(type.vote_average)">&#9734;</span>
                </h5>
            </div>
        </div>
    </div>

</template>

<style lang="scss" scoped>
@use '../partials/styleAllCards.scss' as *
</style>