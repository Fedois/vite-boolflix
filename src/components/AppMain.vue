<script>
import {store} from '../store.js'
import cardsFilm from './cardsFilm.vue'
import cardsSerie from './cardsSerie.vue'

export default {
    name: 'AppMain',
    components: {
        cardsFilm,
        cardsSerie
    },
    data (){
        return{
            store,
        }
    },
}
</script>

<template>
    <main>
       <div class="container">
        <!-- sezione film -->
            <h2 id="films" class="mt-5">FILM</h2>
            <div class="my-cards-films row row-cols-4" v-if="store.listFilm.length > 0">
                <cardsFilm />
            </div>
            <div v-else>
                <h3 class="mt-4">Film non trovato</h3>
            </div>

        <!-- sezione serie -->
            <h2 id="serie-tv" class="mt-5">SERIE-TV</h2>
            <div class="my-cards-series row row-cols-4" v-if="store.listSerie.length > 0">
                <cardsSerie />
            </div>
            <div v-else>
                <h3 class="mt-4">Serie non trovato</h3>
            </div>
       </div> 
    </main>
</template>

<style lang="scss" scoped>
</style>