<script>
import { store } from '../store.js';
    export default {
        name: "AppFooterLink",
        data(){
                return{
                    store
                }
            } 
        }
</script>

<template>
    <div>
        <p>Numero di carte trovate :{{ store.cardObject.length }}</p>
    </div>
</template>

<style lang="scss" scoped>

</style>