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
        axios
            .get('https://api.themoviedb.org/3/movie/550?api_key=9c81a37192d026771ec214401d8ef5f4')
            .then((response) => {
                this.store.listFilm.push(response.data)
                console.log(response.data)
            })
         }
    },
    created(){
        this.writingName()
    }
}
</script>

<template>
    <header>
        BOOLFLIX
        <h1>{{ store.inputNameValue }}</h1>
        <SearchInput @search="writingName" />
    </header>
</template>

<style lang="scss" scoped>
</style>
