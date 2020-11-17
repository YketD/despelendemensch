<template>
    <div class="about-container">
        <div class="image-container">
            <img src="~/assets/img/steven.png">
            <span class="name-label">STEVEN BORGHOUTS</span>
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

        @media (max-width: 1440px) {
            grid-template-columns: 600px auto;
        }

        @media (max-width: 1150px) {
            grid-template-columns: 400px auto;
        }

        @media (max-width: 800px) {
            grid-template-columns: 1fr;
        }

        .image-container {
            position : relative;
            width    : 100%;

            img {
                width : 80%
            }

            .name-label {
                position     : absolute;
                right        : -45px;
                top          : 130px;
                font-size    : 36px;
                background   : #a0bd9f60;
                padding      : 18px;
                padding-left : 136px;
                color        : #8e8e8e;

                @media (max-width: 1440px){
                    top: 110px;
                    padding: 12px;
                    padding-left: 72px;
                    right: -20px;
                }

                @media (max-width: 1150px) {
                    top: 72px;
                    font-size: 24px;
                    padding: 6px;
                    padding-left: 52px;
                }
            }
        }

        .about-text-container {
            margin-left : 64px;

            .about-text {
                font-family : 'ABeeZee', sans-serif;
                color       : #a3a1a1;
                font-size   : 32px;

                @media (max-width: 1440px) {
                    font-size: 22px;
                }@media (max-width: 1150px) {
                    font-size: 18px;
                }
            }
        }
    }
</style>
