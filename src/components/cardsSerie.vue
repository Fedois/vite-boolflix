<script>
import {store} from '../store.js'
export default {
    name: 'cardsSerie',
    data (){
        return{
            store
        }
    }
}
</script>

<template>
    <!-- SERIE -->

    <div class="my-card mb-4 p-2 position-relative" v-for="(serie, index) in store.listSerie">
        <div v-if="serie.poster_path == null" class="poster h-100">
            <img class="d-block w-100 h-100" src="../assets/image-not-found.jpg" :alt="serie.title">
        </div>
        <div v-else class="poster h-100">
            <img class="d-block w-100 h-100" :src="`https://image.tmdb.org/t/p/w342${serie.poster_path}`" :alt="serie.title">
        </div>
        
        <div class="info p-2 h-100 w-100 position-absolute top-0 start-0 d-none">
            <h5 class="title mb-0">titolo:</h5>
            <p class="d-inline-block">{{ serie.name }}</p>
            
            <h5 class="original-title mb-0">titolo originale:</h5>
            <p class="d-inline-block">{{ serie.original_name }}</p>

            <h5 class="overview mb-0">descrizione:</h5>
            <p>{{ serie.overview }}</p>
            
            <h5 class="languages">lingua:
                <img :src="`/src/assets/Flag_${serie.original_language}.svg.png`" :alt="serie.original_language">
            </h5>
            
            <h5 class="vote">voto:
                <span :class="{'yel' : serie.vote_average >= 0}">&#9733;</span>
                <span :class="{'yel' : serie.vote_average > 1}">&#9733;</span>
                <span :class="{'yel' : serie.vote_average > 2}">&#9733;</span>
                <span :class="{'yel' : serie.vote_average > 3}">&#9733;</span>
                <span :class="{'yel' : serie.vote_average > 4}">&#9733;</span>
            </h5>
        </div>
    </div>

</template>

<style lang="scss" scoped>
@use '../partials/styleAllCards.scss' as *
</style>