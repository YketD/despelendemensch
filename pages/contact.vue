<template>
    <div class="about-container">
        <div class="image-container">
            <img src="~/assets/img/contact.png">
        </div>
        <div class="contact-text-container">
            <h1 class="contact-title">SPELENDE WIJS WORDEN?</h1>
            <ul class="contact-container">
                <li>De Spelende Mensch</li>
                <li>Steven Borghouts</li>
                <li>info@despelendemensch.nl</li>
                <li>+31 (0)6 14314166</li>
            </ul>
        </div>
    </div>
</template>

<script>
    export default {
        name: "contact"
    }
</script>

<style lang="scss" scoped>
    .about-container {
        display               : grid;
        grid-template-columns : 1fr 1fr;
        width                 : 100%;

        @media (max-width : 500px) {
            grid-template-columns : 1fr;
        }

        .image-container {
            position : relative;
            width    : 100%;
            text-align: center;

            @media (max-width: 500px) {
                display         : inline-block;
                justify-content : center;
                margin-bottom: 24px;
            }

            img {
                width : 80%;

                @media (max-width: 500px) {
                    width: 60%;
                }
            }
        }

        .contact-text-container {
            display        : flex;
            flex-direction : column;
            align-items    : center;

            @media (max-width : 800px) {
                max-width : 100%;
            }

            .contact-title {
                background : #e39382;
                padding    : 16px 22px;
                display    : inline-block;
                font-size  : 26px;
                margin     : 0;
                height     : fit-content;
                color      : #e9e5e5;
                max-width  : 100%;

                @media (max-width : 1080px) {
                    font-size : 22px;
                }
                @media (max-width : 800px) {
                    font-size : 18px;
                    text-align: center;
                }
            }

            .contact-container {
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
                }

                @media (max-width : 800px) {
                    font-size : 15px;
                }
            }

            @media ('max-width: 800px') {
                margin-left : 0;
            }
        }
    }
</style>
