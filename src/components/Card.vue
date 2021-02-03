<template>
    <div class="cardItem" >
        <div class="cardImagesSide">
            <div class="cardImageSideInner">
                <div class="cardImage" :class="`${card.animation}`" :style="`background-image: url(${card.imagePath})`">
                </div>
            </div>
        </div>
        <div class="cardContextSide">
            <div class="cardTip">
                {{card.tip}}
            </div>
            <div class="cardTitle">
                {{card.title}}
            </div>
            <div class="generalText cardText">
                {{card.text}}
            </div>
            <div v-if="card.searchLink !== ''" class="generalButton">
                Search
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Card",
        props:{
            card:{
                type: Object,
                required: true
            }
        }
    }
</script>

<style scoped>

</style>
