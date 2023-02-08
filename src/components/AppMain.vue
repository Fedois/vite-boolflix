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
            <div class="my-cards row row-cols-4">
                <div class="my-card col" v-for="(film, index) in store.listFilm">
                    <div class="poster">
                        <img src="" alt="">
                    </div>
                    <div class="info">
                        <h5 class="title">titolo:
                            <p class="d-inline-block">{{ film.title }}</p>
                        </h5>
                        <h5 class="original-title">titolo originale:
                            <p class="d-inline-block">{{ film.original_title }}</p>
                        </h5>
                        <h5 class="languages">lingua:
                            <p class="d-inline-block">{{ film.original_language }}</p>
                        </h5>
                        <h5 class="vote">voto:
                            <p class="d-inline-block">{{ film.vote_average }}</p>
                        </h5>
                    </div>
                </div>
            </div>
       </div> 
    </main>
</template>

<style lang="scss" scoped>
</style>