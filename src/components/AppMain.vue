<script>
import {store} from '../store.js'
export default {
    name: 'AppMain',
    data (){
        return{
            store
        }
    }
}
</script>

<template>
    <main>
       <div class="container">
            <div class="my-cards row">
                <div class="my-card col"></div>
            </div>
       </div> 
    </main>
</template>

<style lang="scss" scoped>
</style>