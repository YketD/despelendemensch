<template>
    <div class="podcast-container">
        <img alt="podcast image" :src="img.url" />
        <prismic-rich-text :field="subText" class="label">{{ subText }}</prismic-rich-text>
    </div>
</template>

<script>
    import prismicDOM from 'prismic-dom';

    export default {
        name: "PodcastCard",
        props: ['img', 'subText'],
        computed: {
            formattedDate() {
                return new Date(this.date).toLocaleDateString('NL-nl',
                    { year: 'numeric', month: 'long', day: 'numeric' })
            }
        }
    }
</script>

<style lang="scss" scoped>

    .podcast-container {
        position       : relative;
        font-family    : 'ABeeZee', sans-serif;
        color          : black;
        display        : flex;
        flex-direction : column;
        margin         : auto;

        img {
            max-width          : 100%;
            min-width          : 100%;
            -webkit-box-shadow : rgba(0, 0, 0, 0.3) 0 1px 3px;
            -moz-box-shadow    : rgba(0, 0, 0, 0.3) 0 1px 3px;
            box-shadow         : rgba(0, 0, 0, 0.3) 0 1px 3px;
        }

        .date-label {
            text-decoration : none !important;
            color           : #9d9d9d;
            text-align      : right;
            font-weight     : 300;
            font-size       : 13px;
            line-height     : 15px;
            margin-top: 2px;
        }

        .label {
            text-align      : left;
            display         : inline-block;
            color           : #9d9d9d;
            text-decoration : none !important;
            margin-top      : 6px;

            ::v-deep h1 {
                font-weight : 200;
                font-size   : 21px;

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
