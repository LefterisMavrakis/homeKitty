<template>
        <VueSlickCarousel :arrows="false" :dots="true" dotsClass="slick-dots custom-dot-class">
            <div class="sliderItem" v-for="slide in slides" :key="slide.id" >
                <div class="sliderItemImage" :style="`background-image:url(${slide.imagePath})`">
                </div>
                <div class="sliderItemContext">
                    <div class="sliderItemTitle">
                        {{slide.title}}
                    </div>
                    <div class="sliderItemText">
                        {{slide.text}}
                    </div>
                </div>
            </div>
        </VueSlickCarousel>
</template>

<script>
    import VueSlickCarousel from 'vue-slick-carousel'
    import 'vue-slick-carousel/dist/vue-slick-carousel.css'
    export default {
        name: "Slider",
        components: {
            VueSlickCarousel
        },
        data() {
            return {
                slides: [
                    {
                        id:1,
                        title:'S.und Co',
                        text: 'To take a trivial example, which of us ever undertakes laborious physical exercise, except to obtain some advantage from it?',
                        imagePath:'assets/slideShow/slideImage.jpg'
                    },
                    {
                        id:2,
                        title:'S.btn Co',
                        text: 'S.dmx Co. To take a trivial example, which of us ever undertakes laborious physical exercise, except to obtain some advantage from it?',
                        imagePath:'assets/slideShow/slideImage.jpg'
                    },
                    {
                        id:3,
                        title:'S.dmx Co',
                        text: 'S.dmx Co. To take a trivial example, which of us ever undertakes laborious physical exercise, except to obtain some advantage from it?',
                        imagePath:'assets/slideShow/slideImage.jpg'
                    }
                ]
            }
        }
    }
</script>

<style scoped>

</style>
