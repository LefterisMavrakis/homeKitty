<template>
    <div class="cardsInner">
       <Card v-for="(card, index) in cards" :key="`${index}-${card.id}`" :card="card" />
    </div>
</template>

<script>
    import Card from "./Card";
    export default {
        name: "Cards",
        components:{
            Card
        },
        data() {
            return {
                cards: [
                    {
                        id:1,
                        title:'The Standard',
                        tip:'Since the 1500s',
                        text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt.',
                        imagePath:'assets/cards/mouth.jpg',
                        searchLink:'',
                        animation: 'positioning'
                    },
                    {
                        id:2,
                        title:'The Standard',
                        tip:'Since the 1500s',
                        text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
                        imagePath:'assets/cards/pop-art-love.png',
                        searchLink:'#',
                        animation: 'rotate'
                    },
                ]
            }
        }
    }
</script>

<style scoped>

</style>
