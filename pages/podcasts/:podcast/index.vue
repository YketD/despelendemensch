<template>
    <div class="podcast-container">
        <div class="image-container">
            <img :src="podcast.data.podcast_afbeelding.url">
        </div>

        <div class="description-container">
            <prismic-rich-text class="padding" :field="podcast.data.title"></prismic-rich-text>
            <prismic-rich-text class="padding" :field="podcast.data.subtitle"></prismic-rich-text>
            <prismic-rich-text class="padding" :field="podcast.data.description"></prismic-rich-text>
            <span class="padding" v-if="podcast.data.podcast_links">Luisteren via:&nbsp;
                <a v-for="podcastLink in podcast.data.podcast_links" :href="podcastLink.link.url">
                     <prismic-rich-text :field="podcastLink.link_text" />
                </a>
            </span>
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
        grid-template-columns : .5fr 1fr;
        width                 : 100%;

        @media (max-width : 1440px) {
            grid-template-columns : .75fr 1fr;
        }

        @media (max-width : 800px) {
            grid-template-columns : 1fr;
        }

        .image-container {
            position : relative;
            width    : 100%;

            img {
                width : 100%;
            }
        }
    }

    .description-container {
        ::v-deep div h1 {
            color           : #bac4de;
            text-decoration : none;
            font-size       : 34px;
        }

        ::v-deep div h2 {
            color       : #9c9c9c;
            font-family : 'ABeeZee', sans-serif;
            font-size   : 30px;
        }

        ::v-deep div p {
            font-family : 'ABeeZee', sans-serif;
            color       : #9c9c9c;
            font-size   : 26px;
        }

        a {
            text-decoration : none;
        }

        span {
            display     : flex;
            font-family : 'ABeeZee', sans-serif;
            color       : #9c9c9c;
            font-size   : 34px;
        }

        .padding {
            padding : 12px 24px;
        }

        @media ('max-width: 1380px') {
            ::v-deep div {
                p {
                    font-size : 20px;
                }
                h1 {
                    font-size: 26px;
                }
                h2 {
                    font-size: 24px;
                }
            }
            .padding {
                padding: 6px 12px;
            }
            span {
                font-size: 24px;
            }
        }
    }
</style>
