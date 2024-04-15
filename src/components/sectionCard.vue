<script>
import singleCard from './singleCard.vue';

    export default {
        name: "sectionCard",

        components: {
        singleCard
    },
        data(){
                return{

                }
            } 
        }
        
</script>

<template>
<section>
    <div class="container d-flex p-10">
        <singleCard></singleCard>
        <singleCard></singleCard>
        <singleCard></singleCard>
        <singleCard></singleCard>
        <singleCard></singleCard>
        <singleCard></singleCard>
        <singleCard></singleCard>
        <singleCard></singleCard>
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

    }
}
</style>