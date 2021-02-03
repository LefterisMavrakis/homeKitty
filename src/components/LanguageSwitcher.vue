<template>
    <div class="languageSwitcherWrapper">
        <div class="localeItem"
             v-for="(localeItem,index) in languages" :key="`${index}-${localeItem.id}`"
             :class="{active: localeItem.active}"
             @click="handleClickLocaleItem(localeItem)">
            {{localeItem.name}}
        </div>
    </div>
</template>

<script>
    export default {
        name: "LanguageSwitcher",
        data() {
            return {
                languages: [
                    {id:1, name:'EN', locale:'en',active: true},
                    {id:2, name:'GR', locale:'gr',active: false}
                ]
            }
        },
        methods : {
            handleClickLocaleItem(localeItem) {
                this.languages.forEach(item => {
                    if (localeItem.id === item.id) {
                        item.active = true
                    } else {
                        item.active = false
                    }
                })
            }
        }
    }
</script>

<style scoped>

</style>
