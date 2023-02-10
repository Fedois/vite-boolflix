<script>
import {store} from '../store.js'
import allCards from './allCards.vue'

export default {
    name: 'AppMain',
    components: {
        allCards,
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
            <h2 id="films" class="pt-5">FILM</h2>
            
            <div class="my-cards-films p-3 row row-cols-1 row row-cols-sm-2 row row-cols-md-3 row row-cols-lg-4 row-cols-xl-5" v-if="store.listFilm.length > 0">
                <allCards v-for="film in store.listFilm"
                :type="film" />
            </div>
            
            <div v-else class="p-3">
                <h3 class="mt-4">Film non trovato</h3>
            </div>

        <!-- sezione serie -->
            <h2 id="serie-tv" class="pt-5">SERIE-TV</h2>
            <div class="my-cards-series p-3 row row-cols-1 row row-cols-sm-2 row row-cols-md-3 row row-cols-lg-4 row-cols-xl-5" v-if="store.listSerie.length > 0">
                <allCards v-for="serie in store.listSerie"
                :type="serie" />
            </div>
            
            <div v-else class="p-3">
                <h3 class="mt-4">Serie non trovato</h3>
            </div>
       </div> 
    </main>
</template>

<style lang="scss" scoped>
main{
    height: calc(100vh - 80px);
    overflow: auto;
    scroll-behavior: smooth;

    .container{
        height: 100%;
    }
}
::-webkit-scrollbar {
    width: 5px;
  }
::-webkit-scrollbar-thumb {
background: gray;
border-radius: 50px;
}
::-webkit-scrollbar-thumb:hover {
background: white;
}
</style>