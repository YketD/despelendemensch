<template>
    <div class="menu-container">
        <div class="logo">
            <img src="~/assets/img/despelendemensch.jpg" />
        </div>
        <nav class="navigation">
            <ul>
                <li>
                    <nuxt-link style="color: #A0BD9F" to="/about">ABOUT</nuxt-link>
                </li>
                <li>
                    <nuxt-link style="color: #BAC4DE" to="/" exact>AFLEVERINGEN</nuxt-link>
                </li>
                <li>
                    <nuxt-link style="color: #E19584" to="/contact">CONTACT</nuxt-link>
                </li>
            </ul>
        </nav>
    </div>
</template>

<script>
    export default {
        name: "MenuBar"
    }
</script>

<style lang="scss" scoped>
    .menu-container {
        display         : flex;
        justify-content : space-between;
        margin-bottom: 64px;
        margin-left: -64px;

        .logo {
            width: 256px;
            img {
                width: 100%;
            }
        }

        .navigation {
            display         : flex;
            text-decoration : none;

            ul {
                display : flex;

                li {
                    padding         : 20px;
                    list-style-type : none;
                    font-size: 36px;

                    a {
                        text-decoration : none;
                    }

                    .nuxt-link-active {
                        border-bottom: 3px solid;
                    }
                }
            }
        }
    }
</style>
