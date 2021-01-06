<template>
    <div class="about-container">
        <div class="image-container">
            <img src="~/assets/img/stevenborghoutsWithText.jpg">
        </div>
        <div class="about-text-container">
            <span class="about-text">
                De echte jij is nooit volwassen geworden. Toch vergeten we vaak onszelf te zijn. Hoe wordt je al spelende wijzer in het leven en hoe ontwaak je de inner child? Steven Borghouts beleefde een aaneenschakeling van euforische geluksmomenten op zijn fietstocht naar Istanbul en besloot met bijzondere Menschen hierover in gesprek te gaan. In De Spelende Mensch Podcast onderzoekt hij hoe je een positieve mindset creëert, betekenisvolle dingen kan doen en hoe je dit pad met fun kan belopen.
            </span>
        </div>
    </div>
</template>

<script>
    export default {
        name: "about"
    }
</script>

<style lang="scss" scoped>
    .about-container {
        display               : grid;
        grid-template-columns : 1fr 1fr;
        width                 : 100%;

        @media (max-width: 800px) {
            grid-template-columns: 1fr;
        }

        .image-container {
            position : relative;
            width    : 100%;
            display: flex;
            justify-content: center;

            img {
                width : 80%;
                @media (max-width: 800px) {
                    width: 60%;
                    margin-bottom: 24px;
                }
            }
        }

        .about-text-container {
            margin         : 42px;
            font-family    : 'ABeeZee', sans-serif;
            font-size      : 20px;
            font-weight    : 300;
            line-height    : 30px;
            list-style     : none;
            color          : #a3a1a1;
            display        : flex;
            flex-direction : column;
            padding: 0;

            @media (max-width : 1080px) {
                font-size      : 17px;
                line-height    : 28px;

                margin         : 0 22px 22px;
            }

            @media (max-width : 800px) {
                font-size : 15px;

                margin    : 0 12px 12px;
            }
        }
    }
</style>
