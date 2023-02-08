<script>
import {store} from '../store.js'
export default {
    name: 'AppMain',
    data (){
        return{
            store
        }
    },
}
</script>

<template>
    <main>
       <div class="container">
        <h2 class="mt-5">FILM</h2>
            <div class="my-cards-films row row-cols-4">
                <div class="my-card-film" v-for="(film, index) in store.listFilm">
                    <div class="poster">
                        <img src="" alt="">
                    </div>
                    <div class="info-film">
                        <h5 class="title">titolo:
                            <p class="d-inline-block">{{ film.title }}</p>
                        </h5>
                        <h5 class="original-title">titolo originale:
                            <p class="d-inline-block">{{ film.original_title }}</p>
                        </h5>
                        <h5 v-if="film.original_language == 'en'">
                            <img src="../assets/Flag_of_the_United_Kingdom_(3-5).svg.png" alt="en">
                        </h5>
                        <h5 v-if="film.original_language == 'it'">
                            <img src="../assets/Flag_of_Italy.svg.png" alt="it">
                        </h5>
                        <h5 v-if="film.original_language == 'fr'">
                            <img src="../assets/Francia.jpg" alt="fr">
                        </h5>
                        <h5 v-else class="languages">lingua:
                            <p class="d-inline-block">{{ film.original_language }}</p>
                        </h5>
                        <h5 class="vote">voto:
                            <p class="d-inline-block">{{ film.vote_average }}</p>
                        </h5>
                    </div>
                </div>
            </div>

            <h2 class="mt-5">SERIE-TV</h2>
             <div class="my-cards-films row row-cols-4">
                <div class="my-card-film col" v-for="(serie, index) in store.listSerie">
                    <div class="poster">
                        <img src="" alt="">
                    </div>
                    <div class="info-film">
                        <h5 class="title">titolo:
                            <p class="d-inline-block">{{ serie.name }}</p>
                        </h5>
                        <h5 class="original-title">titolo originale:
                            <p class="d-inline-block">{{ serie.original_name }}</p>
                        </h5>
                        <h5 v-if="serie.original_language == 'en'">
                            <img src="../assets/Flag_of_the_United_Kingdom_(3-5).svg.png" alt="en">
                        </h5>
                        <h5 v-if="serie.original_language == 'it'">
                            <img src="../assets/Flag_of_Italy.svg.png" alt="it">
                        </h5>
                        <h5 v-if="serie.original_language == 'fr'">
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
            </div>
       </div> 
    </main>
</template>

<style lang="scss" scoped>
img{
    width: 20px;
}
</style>