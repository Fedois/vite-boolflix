<script>
import {store} from './store.js'
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'

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
}
</script>

<template>
    <AppHeader />
    <AppMain />
</template>

<style lang="scss">
@use "./main.scss";
body{
    background-color: rgb(30, 30, 30);
    color: white
}
</style>
