<template>
  <div class="templateWrapper mobileNavTemplate">
    <div class="mobileBurgerBtn" :class="{closeBtn: mobileActive}" @click="toggleMobileMenu()">
      <div class="burgerBtnCenter" :class="{active: mobileActive}"  ></div>
    </div>
    <div class="mobileNavigationWrapper flex column" :class="{visible: mobileActive}">
      <div class="mobileNavigationInner">
        <div class="navigationInner">
          <div class="navigationHeader">
            MENU
          </div>
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
        <LanguageSwitcher />
        <div class="mobileFooterWrapper">
          <div class="socialWrapper">
            <div class="socialInner">
              <div class="mobileSocial">
                <div class="socialItem">
                  <img src="assets/social/facebook.svg" />
                </div>
                <div class="socialItem">
                  <img src="assets/social/twitter.svg" />
                </div>
                <div class="socialItem">
                  <img src="assets/social/Instagram.svg" />
                </div>
                <div class="socialItem">
                  <img src="assets/social/browser.svg" />
                </div>
              </div>
              <div class="mobileGdpr">
                Cookies.  |  Privacy.
              </div>
            </div>
          </div>
          <div class="mobileContactInfo">
            <div class="email">
              S.und@themail.com
            </div>
            <div class="phone">
              +30 210 1234 567
            </div>
          </div>
          <div class="mobileCopyrights">
            &copy; The standard Copyright 2020
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<script>
  import LanguageSwitcher from "./LanguageSwitcher";
  export default{
    name: 'MobileNav',
    components:{
      LanguageSwitcher
    },
    data() {
      return {
        navLinks: [
          {id: 1, name: 'Main One', path: '#', active: true},
          {id: 2, name: 'Page Two', path: '#', active: false},
          {id: 3, name: 'Page Three', path: '#', active: false},
          {id: 4, name: 'About Us', path: '#', active: false},
          {id: 5, name: 'Our Work', path: '#', active: false},
          {id: 6, name: 'Contact', path: '#', active: false},
        ],
        mobileActive: false
      }
    },
    methods: {
      toggleMobileMenu() {
        this.mobileActive = !this.mobileActive
      },
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
  };
</script>
