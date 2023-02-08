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
        <h2 id="films" class="mt-5">FILM</h2>
            <div class="my-cards-films row row-cols-4">
                <cardsFilm />
            </div>

        <h2 id="serie-tv" class="mt-5">SERIE-TV</h2>
            <div class="my-cards-series row row-cols-4">
                <cardsSerie />
            </div>
       </div> 
    </main>
</template>

<style lang="scss" scoped>
</style>