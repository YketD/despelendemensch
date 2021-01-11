<template>
    <div class="podcast-container">
        <div class="image-container">
            <img :src="podcast.data.podcast_afbeelding.url">
        </div>

        <div class="description-container">
            <prismic-rich-text class="padding" :field="podcast.data.title"></prismic-rich-text>
            <span class="padding" v-if="podcast.data.podcast_links">Luisteren via:&nbsp;
                <a v-for="podcastLink in podcast.data.podcast_links" :href="podcastLink.link.url">
                     <prismic-rich-text :field="podcastLink.link_text" />
                </a>
            </span>
            <prismic-rich-text class="padding" :field="podcast.data.subtitle"></prismic-rich-text>
            <prismic-rich-text class="padding" :field="podcast.data.description"></prismic-rich-text>
        </div>

    </div>
</template>

<script>
    export default {
        name: "index",
        data() {
            return {
                podcast: {},
            }
        },
        async asyncData({ $prismic, params, error }) {
            try {
                // Query to get post content
                const podcast = (await $prismic.api.getByUID('podcast', params.podcast))

                return {
                    // Set slices as variable
                    podcast
                }
            } catch (e) {
                // Returns error page
                error({ statusCode: 404, message: 'Page not found' })
            }
        },
    }
</script>

<style lang="scss" scoped>
    .podcast-container {
        display               : grid;
        grid-template-columns : 1fr 1fr;
        width                 : 100%;

        @media (max-width : 1440px) {
            grid-template-columns : .75fr 1fr;
        }

        @media (max-width : 500px) {
            grid-template-columns : 1fr;
        }

        .image-container {
            position : relative;
            width    : 100%;

            @media ('max-width:500px') {
                display    : inline-block;
                text-align : center
            }

            img {
                width : 80%;

                @media ('max-width: 500px') {
                    width : 60%;
                }
            }
        }
    }

    .description-container {
        ::v-deep div h1 {
            color           : #bac4de;
            text-decoration : none;
            font-size       : 22px;
            font-weight     : 100;

            @media ('max-width: 500px') {
                font-size : 20px;
            }
        }

        ::v-deep div h2 {
            color       : #9c9c9c;
            font-family : 'ABeeZee', sans-serif;
            font-size   : 18px;
            font-weight : 100;

            @media ('max-width: 500px') {
                font-size : 16px;
            }
        }

        ::v-deep div p {
            font-family : 'ABeeZee', sans-serif;
            color       : #9c9c9c;
            font-size   : 16px;
            font-weight : 100;
            @media ('max-width: 500px') {
                font-size : 15px;
            }
        }

        ::v-deep div span {
            font-family : 'ABeeZee', sans-serif;
            color       : #9c9c9c;
            font-size   : 16px;
            font-weight : 100;

            @media ('max-width: 500px') {
                font-size : 15px;
            }
        }

        a {
            text-decoration : none;
        }

        span {
            display     : flex;
            font-family : 'ABeeZee', sans-serif;
            color       : #9c9c9c;
            font-size   : 18px;
            font-weight : 100;

            @media ('max-width: 500px') {
                font-size : 16px;
            }
        }

        .padding {
            padding : 12px 24px;
        }

        @media ('max-width: 1380px') {

            .padding {
                padding : 6px 12px;
            }
        }
    }
</style>
