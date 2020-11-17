<template>
    <div class="main-container">
        <menu-bar></menu-bar>
        <Nuxt />
    </div>
</template>

<style  lang="scss">
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
        margin: auto;
    }

    *,
    *::before,
    *::after {
        box-sizing : border-box;
        margin     : 0;
    }

    .main-container {
        max-width: 1400px;
        margin: auto;
        margin-top: 24px;

        @media (max-width: 1620px) {
            margin: 82px;
            margin-top: 24px;
        }

    }
</style>
<script>
    import MenuBar from "~/components/MenuBar";
    export default {
        components: { MenuBar }
    }
</script>
