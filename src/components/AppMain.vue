<script>
import {store} from '../store.js'
export default {
    name: 'AppMain',
    data (){
        return{
            store
        }
    }
}
</script>

<template>
    <main>
       <div class="container">
            <div class="my-cards row">
                <div class="my-card col">
                    <div class="poster">
                        <img src="" alt="">
                    </div>
                    <div class="info">
                        <h5 class="title">titolo:
                            <p v-for="film in store.listFilm">{{ film.title }}</p>
                        </h5>
                        <h5 class="original-title">titolo originale:
                            <p v-for="film in store.listFilm">{{ film.original_title }}</p>
                        </h5>
                        <h5 class="lenguages">lingua:
                            <p v-for="film in store.listFilm">{{ film.spoken_languages[0].iso_639_1 }}</p>
                        </h5>
                        <h5 class="voto">voto:
                            <p v-for="film in store.listFilm">{{ film.vote_average }}</p>
                        </h5>
                    </div>
                </div>
            </div>
       </div> 
    </main>
</template>

<style lang="scss" scoped>
</style>