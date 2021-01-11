<template>
    <div class="podcast-container">
        <div class="podcast-grid">
            <nuxt-link v-for="podcast in podcasts" class="no-underline" :to="'podcasts/' + podcast.uid">
                <podcast-card
                    :title="podcast.data.title"
                    :img="podcast.data.podcast_afbeelding"
                    :date="podcast.first_publication_date"
                    :sub-text="podcast.data.title"
                    class="podcast-card" />
            </nuxt-link>
        </div>
        {{ document }}

    </div>
</template>

<script>
    import PodcastCard from "~/components/PodcastCard";

    export default {
        components: { PodcastCard },
        methods: {
            redirect(link) {
                this.window.href = link;
            }
        },
        data() {
            return {
                podcasts: [],
            }
        },
        async asyncData({ $prismic, error }) {
            try {
                const podcasts = (await $prismic.api.query(
                    $prismic.predicates.at('document.type', 'podcast')
                )).results;
                return {
                    podcasts
                }
            } catch (e) {
                console.log(e)
                error({ statusCode: 404, message: 'Page not found' })
            }
        },
    }
</script>

<style lang="scss">
    .container {
        margin          : 0 auto;
        min-height      : 100vh;
        display         : flex;
        justify-content : center;
        align-items     : center;
        text-align      : center;

        @media ('max-width: 500px') {
            min-height : 0;
        }
    }

    .no-underline {
        text-decoration : none !important;
    }

    .podcast-grid {
        display               : grid;
        grid-template-columns : repeat(3, 1fr);
        grid-gap              : 24px;
        justify-content       : center;

        @media ('max-width :720px') {
            grid-template-columns : repeat(2, 1fr);
        }

        @media ('max-width : 400px') {
            grid-template-columns : repeat(1, 1fr);
        }

        .podcast-card {
            max-width : 300px;
            min-width : 150px;

            @media ('max-width: 500px') {
                width : 100%;
            }
        }
    }

</style>
