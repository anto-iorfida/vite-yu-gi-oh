<script>
    export default {
        name: "singleCard",
        props :{
            cardInfo: Object
        }
        }
</script>

<template>
<div class="card d-flex">
    <div class="image">
        <img :src="cardInfo.card_images[0].image_url_small" alt="">
    </div>
    <h4>{{cardInfo.name}}</h4>
    <p v-if="cardInfo.archetype && cardInfo.archetype.length > 0">{{ cardInfo.archetype }}</p>
    <p v-else>Not specific</p>

</div>
</template>

<style lang="scss" scoped>
@use '../style/variable' as*;

.card{
    width: calc((100% / 5 ) - 10px);
    background-color: $primary-color ;
    border-radius: 10px;
    text-align: center;
    margin: 5px;
    flex-direction: column;
    justify-content: space-between;

    *{
        margin-bottom: 8px;
    }
    h4{
        color: white;
        font-size: small;
    }
}

</style>