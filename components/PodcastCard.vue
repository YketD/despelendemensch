<template>
    <div class="podcast-container">
        <img :src="img.url" />
        <prismic-rich-text :field="subText" class="label">{{ subText }}</prismic-rich-text>
        <prismic-rich-text :field="title" class="subtext">{{ title }}</prismic-rich-text>
    </div>
</template>

<script>
    import prismicDOM from 'prismic-dom';

    export default {
        name: "PodcastCard",
        props: ['title', 'img', 'subText']
    }
</script>

<style lang="scss" scoped>

    .podcast-container {
        position : relative;

        img {
            max-width : 100%;
            min-width : 100%;
        }

        .label {
            position   : absolute;
            right      : 0;
            top        : 54px;
            max-width  : 70%;
            font-size  : 36px;
            background : rgba(160, 189, 159, .6);
            color      : #ffffff;
            padding    : 12px;

            @media ('max-width: 500px') {
                font-size : 24px;
            }
            @media ('max-width: 360px') {
                font-size : 12px;
            }
        }

        .subtext {
            text-align      : left;
            font-family     : 'ABeeZee', sans-serif;
            display         : inline-block;
            text-decoration : none !important;
            color           : #9d9d9d;

            ::v-deep h1 {
                @media ('max-width: 500px') {
                    font-size : 24px;
                }
                @media ('max-width: 360px') {
                    font-size : 16px;
                }
            }

        }
    }
</style>
