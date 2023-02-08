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
    <!-- SERIE-TV -->

    <div class="my-card-film col" v-for="(serie, index) in store.listSerie">
        <div v-if="serie.poster_path == null" class="poster">
            <img src="../assets/image-not-found.jpg" alt="">
        </div>
        <div v-else class="poster">
            <img :src="`https://image.tmdb.org/t/p/w342${serie.poster_path}`" :alt="serie.title">
        </div>
        <div class="info-film">
            <h5 class="title">titolo:
                <p class="d-inline-block">{{ serie.name }}</p>
            </h5>
            
            <h5 class="original-title">titolo originale:
                <p class="d-inline-block">{{ serie.original_name }}</p>
            </h5>
            
            <h5 v-if="serie.original_language == 'en'" class="languages">lingua:
                <img src="../assets/Flag_of_the_United_Kingdom_(3-5).svg.png" alt="en">
            </h5>
            
            <h5 v-else-if="serie.original_language == 'it'" class="languages">lingua:
                <img src="../assets/Flag_of_Italy.svg.png" alt="it">
            </h5>
            <h5 v-else-if="serie.original_language == 'fr'" class="languages">lingua:
                <img src="../assets/Francia.jpg" alt="fr">
            </h5>
            <h5 v-else class="languages">lingua:
                <p class="d-inline-block">{{ serie.original_language }}</p>
            </h5>
            <h5 class="vote">voto:
                <p class="d-inline-block">{{ serie.vote_average }}</p>
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