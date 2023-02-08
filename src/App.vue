<script>
import {store} from './store.js'
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'
import axios from 'axios'

export default {
    name: 'App',
    components: {
        AppHeader,
        AppMain
    },
    data (){
        return{
            store
        }
    },
    created () {
        axios
            .get('https://api.themoviedb.org/3/movie/550?api_key=9c81a37192d026771ec214401d8ef5f4')
            .then((response) => {
            console.log(response)
            })
    }
}
</script>

<template>
<AppHeader />
<AppMain />
</template>

<style lang="scss">
@use "./main.scss";
</style>
