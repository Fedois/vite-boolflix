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
    }
}
</script>

<template>
    <header>
        BOOLFLIX
        <h1>{{ store.inputNameValue }}</h1>
        <SearchInput />
    </header>
</template>

<style lang="scss" scoped>
</style>
