<template>
    <div id="app">
        <div class="appWrapper">
            <div ref="headerWrapper" id="headerWrapper" class="headerWrapper">
                <div class="constraintLg">
                    <div class="headerInner">
                        <div class="logoWrapper">
<!--                            <img class="logo" src="./assets/SLogo.svg" alt="S Logo"/>-->
                            <svg width="72px" height="72px" viewBox="0 0 72 72" version="1.1" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns="http://www.w3.org/2000/svg">
                                <desc>Created with Lunacy</desc>
                                <defs>
                                    <path d="M0 0L72 0L72 72L0 72L0 0Z" id="path_1" />
                                    <clipPath id="mask_1">
                                        <use xlink:href="#path_1" />
                                    </clipPath>
                                </defs>
                                <g id="SLogo">
                                    <path d="M0 0L72 0L72 72L0 72L0 0Z" id="Background" fill="none" fill-rule="evenodd" stroke="none" />
                                    <g clip-path="url(#mask_1)">
                                        <g id="Group" transform="translate(-0.005340576 -0.0040740967)">
                                            <g id="Group" transform="translate(57.005333 54.00407)">
                                                <path d="M0 7.5C0 3.35786 3.35786 0 7.5 0C11.6421 0 15 3.35786 15 7.5C15 11.6421 11.6421 15 7.5 15C3.35786 15 0 11.6421 0 7.5Z" id="Circle" fill="#B4FF00" fill-rule="evenodd" stroke="none" />
                                            </g>
                                            <path d="M54.0053 24.0051L54.0053 22.4051C54.0603 18.262 52.8982 14.1939 50.6633 10.705C48.3803 7.22641 45.1547 4.4691 41.3633 2.75508C37.1868 0.869416 32.6452 -0.0699759 28.0633 0.00405979C23.506 -0.0570669 18.983 0.799256 14.7634 2.52207C11.0177 4.00308 7.76391 6.50737 5.37334 9.74909C3.15716 12.871 1.98717 16.6148 2.03136 20.4431C2.03133 28.0561 6.11632 34.1511 14.1713 38.5601C17.8375 40.4495 21.6625 42.0132 25.6023 43.2331C30.0673 44.6971 33.1573 46.0741 34.7854 47.3241C36.1471 48.3893 36.887 50.0641 36.7573 51.7881C36.8486 53.3765 36.1151 54.9 34.8163 55.8191C32.8939 57.0237 30.6414 57.5936 28.3773 57.4481C18.4023 57.4481 18.0033 51.9191 18.0033 47.9991L18.0033 46.4991L0.00334746 46.4991L0.00334746 48.3191C-0.0735263 52.7071 1.17522 57.0162 3.58639 60.6831C6.14742 64.3796 9.7044 67.2739 13.8444 69.0301C18.4218 71.0439 23.3769 72.0558 28.3773 71.9981C36.0193 71.9981 42.2263 70.2211 46.8274 66.7181C51.5893 63.0911 54.0044 58.0371 54.0044 51.6961C54.1292 46.3276 52.0188 41.1484 48.1774 37.3961C44.4664 33.7331 38.5593 30.6461 30.6234 28.2311C27.4597 27.3738 24.434 26.0708 21.6374 24.3611C19.4824 22.8961 19.2374 21.4471 19.2374 20.4831C19.1821 18.8642 19.9407 17.3251 21.2584 16.3831C22.7514 15.2291 24.9674 14.6441 27.8414 14.6441C30.7854 14.6441 33.0574 15.3441 34.5914 16.7101C36.0804 18.0391 36.0054 19.9001 36.0054 22.4031L36.0054 24.0031L54.0053 24.0051Z" id="Shape" fill="#B4FF00" fill-rule="evenodd" stroke="none" />
                                        </g>
                                    </g>
                                </g>
                            </svg>
                        </div>
                        <Navigation/>
                        <LanguageSwitcher/>
                    </div>
                </div>
            </div>
            <div ref="bodyWrapper" id="bodyWrapper" class="bodyWrapper">
                <div ref="sliderWrapper" class="sliderWrapper">
                    <Slider/>
                </div>
                <div class="cardsWrapper">
                    <div class="constraintMd">
                        <div class="cardsInner">
                            <Cards />
                        </div>
                    </div>
                </div>
                <div class="contactWrapper">
                    <Contact />
                </div>
            </div>
            <div class="footerWrapper">
                <div class="constraintLg">
                    <footer class="footerInner">
                        <div class="copyrights">
                            The standard Copyright 2020
                        </div>
                        <div class="gdpr">
                            Cookies | Privacy
                        </div>
                        <div class="footerLogo">
                            <svg width="32px" height="32px" viewBox="0 0 32 32" version="1.1" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns="http://www.w3.org/2000/svg">
                                <desc>Created with Lunacy</desc>
                                <g id="Group" transform="translate(0 -0.00076293945)">
                                    <g id="Group" transform="translate(24.995485 24.000778)">
                                        <path d="M0 3.5C0 1.567 1.567 0 3.5 0C5.433 0 7 1.567 7 3.5C7 5.433 5.433 7 3.5 7C1.567 7 0 5.433 0 3.5Z" id="Circle" fill="#B4FF00" fill-rule="evenodd" stroke="none" />
                                    </g>
                                    <path d="M23.9955 10.6678L23.9955 9.95778C24.02 8.1165 23.5037 6.30847 22.5105 4.7578C21.4959 3.21188 20.0624 1.98653 18.3775 1.22478C16.5216 0.38681 14.5035 -0.030808 12.4675 0.00176954C10.442 -0.0254674 8.43183 0.355087 6.55649 1.12079C4.89185 1.77907 3.44583 2.89207 2.38346 4.33278C1.39859 5.72037 0.878725 7.38434 0.8985 9.0858C0.8985 12.4688 2.7135 15.1788 6.29849 17.1378C7.92807 17.9776 9.62827 18.6726 11.3795 19.2148C12.8226 19.6147 14.198 20.2274 15.4605 21.0328C16.0659 21.5061 16.395 22.2505 16.3375 23.0168C16.3781 23.723 16.0519 24.4002 15.4745 24.8088C14.62 25.3442 13.6188 25.5975 12.6125 25.5328C8.17948 25.5328 8.0015 23.0748 8.0015 21.3328L8.0015 20.6658L0.001497 20.6658L0.001497 21.4748C-0.0327742 23.4249 0.522096 25.34 1.59354 26.9698C2.73172 28.6128 4.31253 29.8992 6.1525 30.6798C8.18692 31.5748 10.3891 32.0245 12.6115 31.9988C15.5288 32.1413 18.4115 31.3162 20.8116 29.6518C22.9071 28.0852 24.0995 25.5893 24.0015 22.9748C24.0571 20.5892 23.119 18.2877 21.4115 16.6208C19.1667 14.6704 16.4948 13.2752 13.6115 12.5478C12.2054 12.1668 10.8606 11.5877 9.61756 10.8278C8.97287 10.4919 8.5632 9.8306 8.54956 9.10378C8.52481 8.38335 8.86276 7.69844 9.44956 7.27977C10.3142 6.70936 11.342 6.43787 12.3756 6.50677C13.4545 6.43243 14.523 6.75935 15.3756 7.42477C16.0375 8.01578 16.0045 8.84277 16.0045 9.95477L16.0045 10.6648L23.9955 10.6678Z" id="Shape" fill="#B4FF00" fill-rule="evenodd" stroke="none" />
                                </g>
                            </svg>
                        </div>
                    </footer>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import Navigation from "./components/Navigation";
    import LanguageSwitcher from "./components/LanguageSwitcher";
    import Slider from "./components/Slider";
    import Cards from "./components/Cards";
    import Contact from "./components/Contact";

    export default {
        name: 'App',
        components: {
            Navigation,
            LanguageSwitcher,
            Slider,
            Cards,
            Contact
        },
        methods: {
            giveBodyMarginTop () {
                const headerHeight = this.$refs.headerWrapper.offsetHeight
                this.$refs.bodyWrapper.style.paddingTop = headerHeight + 'px'
                // this.$refs.sliderWrapper.style.height = `calc(100vh - ${headerHeight}px )`
            }
        },
        mounted(){
            this.giveBodyMarginTop()
        }
    }
</script>

<style>
    @import './css/app.css';
</style>
