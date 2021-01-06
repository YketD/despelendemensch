<template>
    <div class="main-container">
        <menu-bar class="main-width"></menu-bar>
        <div class="content-width">
            <transition name="fade" mode="out-in">
                <Nuxt />
            </transition>
        </div>
    </div>
</template>

<style lang="scss">
    html {
        font-family              : 'Abadi MT Condensed Extra', sans-serif;
        font-size                : 16px;
        font-weight              : 800;
        font-style               : normal;
        word-spacing             : 1px;
        -ms-text-size-adjust     : 100%;
        -webkit-text-size-adjust : 100%;
        -moz-osx-font-smoothing  : grayscale;
        -webkit-font-smoothing   : antialiased;
        box-sizing               : border-box;
    }

    body {
        margin : auto;
    }

    *,
    *::before,
    *::after {
        box-sizing : border-box;
        margin     : 0;
    }

    .main-container {
        max-width  : 1200px;
        margin     : auto;
        margin-top : 24px;

        @media (max-width : 1620px) {
            margin-top : 24px;
        }

        @media(max-width : 1280px) {
            margin : 42px;
        }

        .main-width {
            max-width : 1200px;
        }

        .content-width {
            max-width : 1100px;
            margin: auto;
        }

    }

    .fade-enter-active, .fade-leave-active {
        transition : opacity 1s;
    }

    .fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */
    {
        opacity : 0;
    }
</style>
<script>
    import MenuBar from "~/components/MenuBar";

    export default {
        components: { MenuBar }
    }
</script>
