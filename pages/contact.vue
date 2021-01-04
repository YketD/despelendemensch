<template>
    <div class="about-container">
        <div class="image-container">
            <img src="~/assets/img/contact.png">
        </div>
        <div class="about-text-container">
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

        @media (max-width : 1440px) {
            grid-template-columns : 600px auto;
        }

        @media (max-width : 1150px) {
            grid-template-columns : 400px auto;
        }

        @media (max-width : 800px) {
            grid-template-columns : 1fr;
        }

        .image-container {
            position : relative;
            width    : 100%;

            img {
                width : 80%;

                @media (max-width: 800px) {
                    width: 100%
                }
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

                @media (max-width : 1440px) {
                    top          : 110px;
                    padding      : 12px;
                    padding-left : 72px;
                    right        : -20px;
                }

                @media (max-width : 1150px) {
                    top          : 72px;
                    font-size    : 24px;
                    padding      : 6px;
                    padding-left : 52px;
                }
            }
        }

        .about-text-container {
            margin-left    : 64px;
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
                font-size  : 52px;
                margin     : 0;
                height     : fit-content;
                color      : #e9e5e5;
                max-width  : 80%;

                @media (max-width : 800px) {
                    font-size : 32px;
                    width: 100%;
                    text-align: center;
                }
            }

            .contact-container {
                margin         : 42px;
                font-family    : 'ABeeZee', sans-serif;
                font-size      : 32px;
                font-weight    : 400;
                line-height    : 56px;
                list-style     : none;
                color          : #a3a1a1;
                display        : flex;
                flex-direction : column;

                @media (max-width : 800px) {
                    font-size : 22px;
                    text-align: center;
                    padding: 0;
                }
            }

            @media ('max-width: 800px') {
                margin-left : 0;
            }

            .about-text {
                font-family : 'ABeeZee', sans-serif;
                color       : #a3a1a1;
                font-size   : 32px;

                @media (max-width : 1440px) {
                    font-size : 22px;
                }
                @media (max-width : 1150px) {
                    font-size : 18px;
                }
            }
        }
    }
</style>
