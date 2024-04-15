<script>
    export default {
        name: "singleCard",
        data(){
                return{

                }
            } 
        }
</script>

<template>
<div class="card">
    <div class="image">
        <img src="https://images.ygoprodeck.com/images/cards_small/34541863.jpg" alt="">
    </div>
    <h4>A CELL BREDIJK FRFWEF</h4>
    <p>Alien</p>
</div>
</template>

<style lang="scss" scoped>
@use '../style/variable' as*;

.card{
    width: calc((100% / 5 ) - 10px);
    background-color: $primary-color ;
    text-align: center;
    margin: 5px;

    *{
        margin-bottom: 14px;
    }
    h4{
        color: white;
        font-size: small;
    }
}

</style>