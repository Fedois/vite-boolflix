<script>
import {store} from '../store.js'
export default {
    name: 'SearchInput',
    data (){
        return{
            store
        }
    }
}
</script>

<template>
    <div>
        <form action="">
            <input type="text" v-model="store.inputNameValue">
            <button type="submit">cerca</button>
        </form>
    </div>
</template>

<style lang="scss" scoped>
</style>