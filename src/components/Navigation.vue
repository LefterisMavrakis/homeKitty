<template>
    <div class="navWrapper">
        <nav>
            <div v-for="(navLink, index) in navLinks"
                 class="navItem"
                 :class="{active: navLink.active}"
                 :key="`${index}-${navLink.id}`"
                 @click="handleClickNavLink(navLink)">
                <a :href="navLink.path">{{navLink.name}}</a>
            </div>
        </nav>
    </div>
</template>

<script>
    export default {
        name: "Navigation",
        data() {
            return {
                navLinks: [
                    {id: 1, name: 'Main One', path: '#', active: true},
                    {id: 2, name: 'Page Two', path: '#', active: false},
                    {id: 3, name: 'Page Three', path: '#', active: false},
                    {id: 4, name: 'About Us', path: '#', active: false},
                    {id: 5, name: 'Our Work', path: '#', active: false},
                    {id: 6, name: 'Contact', path: '#', active: false},
                ]
            }
        },
        methods: {
            handleClickNavLink(navLink) {
                this.navLinks.forEach(link => {
                    if (navLink.id === link.id) {
                        link.active = true
                    } else {
                        link.active = false
                    }
                })
            },

        }
    }
</script>

<style scoped>

</style>
