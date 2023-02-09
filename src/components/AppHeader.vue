<script>
import {store} from '../store.js'
import axios from 'axios'
import SearchInput from './SearchInput.vue'
export default {
    name: 'AppHeader',
    components: {
        SearchInput
    },
    data (){
        return{
            store
        }
    },
    methods: {
        writingTitle(){
            this.store.loading = true

            if(this.store.inputNameValue != ''){
                axios
                    .get('https://api.themoviedb.org/3/search/movie?api_key=9c81a37192d026771ec214401d8ef5f4&query=' + this.store.inputNameValue)
                    .then((response) => {
                        this.store.listFilm = response.data.results
                        // console.log(response.data.results)
                        this.store.loading = false

                    })
                axios
                    .get('https://api.themoviedb.org/3/search/tv?api_key=9c81a37192d026771ec214401d8ef5f4&query=' + this.store.inputNameValue)
                    .then((response) => {
                        this.store.listSerie = response.data.results
                        // console.log(response.data.results)
                        this.store.loading = false
                    })
            }
            else{
                axios
                    .get('https://api.themoviedb.org/3/search/movie?api_key=9c81a37192d026771ec214401d8ef5f4&query=ritorno+al+futuro')
                    .then((response) => {
                        this.store.listFilm = response.data.results
                        // console.log(response.data.results)
                    })
                axios
                    .get('https://api.themoviedb.org/3/search/tv?api_key=9c81a37192d026771ec214401d8ef5f4&query=ritorno+al+futuro')
                    .then((response) => {
                        this.store.listSerie = response.data.results
                        // console.log(response.data.results)
                    })
            }
            }
    },
    created(){
        this.writingTitle()
    }
}
</script>

<template>
    <header class="sticky-top">
        <div class="container-fluid d-flex justify-content-between align-items-center h-100">
            <div class="logo&nav">
                <h1 class="d-inline-block">BOOLFLIX</h1>

                <nav class="d-inline-block">
                    <ul class="m-0">
                        <li class="d-inline-block me-3">
                            <a class="text-white text-decoration-none" href="#films">FILM</a>
                        </li>
                        <li class="d-inline-block me-3">
                            <a class="text-white text-decoration-none" href="#serie-tv">SERIE-TV</a>
                        </li>
                    </ul>
                </nav>
            </div>
            
            <SearchInput @search="writingTitle" />
        </div>
    </header>
</template>

<style lang="scss" scoped>
header{
    background-color: black;
    color: red;
    height: 80px;

    ul{
        list-style: none;

        li:hover{
            border-bottom: 1px solid red;
        }
    }
}
</style>
