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
        writingName(){
            if(this.store.inputNameValue != ''){
                axios
                    .get('https://api.themoviedb.org/3/search/movie?api_key=9c81a37192d026771ec214401d8ef5f4&query=' + this.store.inputNameValue)
                    .then((response) => {
                        this.store.listFilm = response.data.results
                        console.log(response.data.results)
                    })
            }
            else{
                axios
                    .get('https://api.themoviedb.org/3/search/movie?api_key=9c81a37192d026771ec214401d8ef5f4&query=ritorno+al+futuro')
                    .then((response) => {
                        this.store.listFilm = response.data.results
                        console.log(response.data.results)
                    })
            }
            }
    },
    created(){
        this.writingName()
    }
}
</script>

<template>
    <header>
        <div class="container-fluid">
            <h1>BOOLFLIX</h1>
            <!-- <h1>{{ store.inputNameValue }}</h1> -->
            <SearchInput @search="writingName" />
        </div>
    </header>
</template>

<style lang="scss" scoped>
</style>
