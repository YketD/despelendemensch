<template>
    <div class="podcast-container">
        <img :src="img" />
        <div class="label">{{title}}</div>
        <div class="subtext">{{subText}}</div>
    </div>
</template>

<script>
    export default {
        name: "PodcastCard",
        props: ['title', 'img', 'subText']
    }
</script>

<style lang="scss" scoped>

    .podcast-container {
        position : relative;

        img{
            max-width: 100%;
            min-width: 100%;
        }

        .label {
            position: absolute;
            right: 0;
            top: 54px;
            max-width: 70%;
            font-size: 36px;
            background: rgba(160,189,159,.6);
            color: #fff;
            padding: 12px;
        }

        .subtext {
            text-align: left;
            font-family: 'ABeeZee', sans-serif;
            display:inline-block;
            text-decoration:none !important;
            color: #9D9D9D;
        }
    }
</style>
