<template>
    <div class="menu">
        <div class="menu-container">
            <div class="logo">
                <img src="~/assets/img/despelendemensch.jpg" />
            </div>
            <nav class="navigation">
                <div @click="mobileMenuIsOpen = !mobileMenuIsOpen" class="hamburger">
                    <svg viewBox="0 0 100 80" width="30" height="30">
                        <rect fill="#A0BD9F" width="100" height="15"></rect>
                        <rect fill="#BAC4DE" y="30" width="100" height="15"></rect>
                        <rect fill="#E19584" y="60" width="100" height="15"></rect>
                    </svg>
                </div>

                <ul>
                    <li>
                        <nuxt-link style="color: #a0bd9f" to="/about">ABOUT</nuxt-link>
                    </li>
                    <li >
                        <nuxt-link  style="color: #bac4de" to="/" exact>AFLEVERINGEN</nuxt-link>
                    </li>
                    <li>
                        <nuxt-link style="color: #e19584" to="/contact">CONTACT</nuxt-link>
                    </li>
                </ul>

            </nav>
        </div>
        <transition name="slide">
            <div v-if="mobileMenuIsOpen" class="mobile-menu">
            <ul>
                <li>
                    <nuxt-link style="color: #a0bd9f" to="/about">ABOUT</nuxt-link>
                </li>
                <li>
                    <nuxt-link style="color: #bac4de" to="/" exact>AFLEVERINGEN</nuxt-link>
                </li>
                <li>
                    <nuxt-link style="color: #e19584" to="/contact">CONTACT</nuxt-link>
                </li>
            </ul>
        </div>
        </transition>
    </div>
</template>

<script>
    export default {
        name: "MenuBar",
        data() {
            return {
                mobileMenuIsOpen: false,
            }
        },
        watch: {
            '$route' () {
                this.mobileMenuIsOpen = false;
            }
        }
    }
</script>

<style lang="scss" scoped>
    .menu {
        position : relative;
    }

    .menu-container {
        display         : flex;
        justify-content : space-between;
        margin-bottom   : 64px;
        margin-left     : -64px;

        @media ('max-width: 1280px') {
            margin-left : 0;
        }

        @media ('max-width: 500px') {
            margin-bottom: 12px;
        }

        .logo {
            width : 172px;

            @media(max-width : 1080px) {
                width : 152px
            }

            @media(max-width : 500px) {
                width : 50%;
            }

            img {
                width : 100%;
            }
        }

        .navigation {
            display         : flex;
            text-decoration : none;

                ul {
                display : flex;

                @media ('max-width: 500px') {
                    display : none;
                }

                li {
                    padding         : 20px;
                    list-style-type : none;
                    font-size       : 22px;

                    @media ('max-width: 1080px') {
                        font-size : 18px;
                    }
                    @media ('max-width: 720px') {
                        font-size : 15px;
                    }

                    a {
                        text-decoration : none;
                    }

                    .nuxt-link-active {
                        border-bottom : 3px solid;
                    }
                }
            }

            .hamburger {
                display : none;
                @media (max-width : 500px) {
                    display : flex;
                    justify-content: center;
                    align-items: center;
                    width: 100%;
                }
            }
        }
    }

    .mobile-menu {
        transition: height .5s ;
        width   : 100%;

        ul {
            list-style-type: none;
            padding: 0;
            display: flex;
            justify-content: space-evenly;
            height: 200px;
            flex-direction: column;
            box-shadow: -6px 3px -6px rgba(0,0,0,0.16), -6px 3px 6px rgba(0,0,0,0.23);

            li {
                width: 100%;
                text-align: center;
                padding: 6px;
                font-size: 32px;
            }
        }
    }

    .slide-enter-to, .slide-leave {
        height : 200px;
        overflow   : hidden;
    }

    .slide-enter, .slide-leave-to {
        overflow   : hidden;
        height : 0;
    }
</style>
