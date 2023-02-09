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
        <form action="" @submit.prevent="$emit('search')">
            <input class="p-1" type="text" v-model="store.inputNameValue" placeholder='example "back to the future"'>
            <button class="p-1" type="submit">Search</button>
        </form>
    </div>
</template>

<style lang="scss" scoped>
input{
    width: 300px;
}
</style>