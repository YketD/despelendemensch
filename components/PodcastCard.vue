<template>
    <div class="podcast-container">
        <img :src="img.url" />
        <span class="date-label">{{ formattedDate }}</span>
        <prismic-rich-text :field="subText" class="label">{{ subText }}</prismic-rich-text>
    </div>
</template>

<script>
    import prismicDOM from 'prismic-dom';

    export default {
        name: "PodcastCard",
        props: ['img', 'subText', 'date'],
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
        position    : relative;
        font-family : 'ABeeZee', sans-serif;
        color       : black;
        display: flex;
        flex-direction: column;
        margin: auto    ;
        img {
            max-width : 100%;
            min-width : 100%;
        }

        .date-label {
            text-decoration : none !important;
            color           : #9d9d9d;
            text-align: right;
            margin-bottom: 6px;
        }

        .label {
            text-align      : left;
            display         : inline-block;
            color           : #9d9d9d;
            text-decoration : none !important;

            ::v-deep h2 {
                font-weight : 200;

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
