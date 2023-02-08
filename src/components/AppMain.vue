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
       <div class="my-container border">
        <h2>FILM</h2>
            <div class="my-cards-films row">
                <div class="my-card-film col" v-for="(film, index) in store.listFilm">
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
                        <h5 class="languages">lingua:
                            <p class="d-inline-block">{{ film.original_language }}</p>
                        </h5>
                        <h5 class="vote">voto:
                            <p class="d-inline-block">{{ film.vote_average }}</p>
                        </h5>
                    </div>
                </div>
            </div>

            <h2>SERIE-TV</h2>
             <div class="my-cards-films row">
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
                        <h5 class="languages">lingua:
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
.my-container{
    width: 1200px;
    height: 100%;
    margin: 0 auto;

    .my-cards-films{
        width: 100%;
        scroll-behavior: auto;
    }
}
</style>