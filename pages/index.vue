<template>
    <div class="container">
        <div class="podcast-grid">
            <nuxt-link v-for="podcast in podcasts" :to="'podcasts' + podcast.link">
                <podcast-card
                    :title="podcast.title"
                    :img="podcast.img"
                    :sub-text="podcast.subText"
                    class="podcast-card" />
            </nuxt-link>
        </div>

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
                podcasts: [
                    {
                        title: '3000 KM fietsen in 18 dagen',
                        img: 'https://picsum.photos/1200?grayscale',
                        link: '/abc',
                        subText: 'MENSCH 1: Steven Borghouts'
                    }, {
                        title: 'BILLY EN ZIJN LIEFDE VOOR 3D BRILLEN ',
                        img: 'https://picsum.photos/650?grayscale',
                        link: '/abc',
                        subText: 'MENSCH 2: Billy Brabo'
                    }, {
                        title: 'WHEELIE QUEEN SUMMER ‘69',
                        img: 'https://picsum.photos/500?grayscale',
                        link: '/abc',
                        subText: 'MENSCH 3: Gerda Assink'
                    }, {
                        title: 'test',
                        img: 'https://picsum.photos/450?grayscale',
                        link: '/abc',
                        subText: 'MENSCH 3: Gerda Assink'
                    },
                ]
            }
        }
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
    }

    .podcast-grid {
        display               : grid;
        grid-template-columns : repeat(3, 1fr);
        grid-gap              : 24px;

        .podcast-card {
            width : 400px;
        }
    }

</style>
