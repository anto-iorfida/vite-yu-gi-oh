<script>
import { store } from '../store.js';
import singleCard from './singleCard.vue';
import AppLoader from './AppLoader.vue';
import numResult from './numResult.vue';

    export default {
        name: "sectionCard",

        components: {
        singleCard,
        AppLoader,
        numResult
    },
        data(){
                return{
                    store
                }
            } 
        }
        
</script>

<template>
<section>
    <numResult></numResult>
    <div class="container d-flex p-10">
        <singleCard v-if="!store.isLoading" v-for="card in store.cardObject" :key="card.id" :cardInfo="card"></singleCard>
        <AppLoader v-else></AppLoader>
        
    </div>
</section>
</template>

<style lang="scss" scoped>
@use '../style/variable' as*;
section{
    background-color: $primary-color ;
    padding: 6px;
    .container{
        flex-wrap: wrap;
        background-color: white;
        border: 4px solid darkred;
    }
}
</style>