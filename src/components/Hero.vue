<template>
    <div class="hero-container">
        <div class="hero-content">
            <h5>{{ text.subtitle.toUpperCase() }}</h5>
            <h1>{{ text.title }}</h1>
            <div class="green-divider">
                <div class="left-divider"></div>
                <div class="right-divider"></div>
            </div>
            <p>{{ text.text }}</p>

            <Button :text="'read more'" :type="'secondary'"></Button>

            <ul class="social-list">
                <li v-for="social in socialList" :key="social.name">
                    <a :href="social.link">{{ social.name.toUpperCase() }}</a>
                </li>
            </ul>
        </div>

        <img src="@/assets/img/Group-35-2x.png" alt="hero-image">
    </div>
</template>

<script>
import Button from './Button.vue'

export default {
    name: 'Hero',
    components: { Button },
    props: { text: Object },
    data() {
        return {
            socialList: [
                {
                    name: 'facebook',
                    link: 'www.facebook.com'
                },
                {
                    name: 'instagram',
                    link: 'www.instagram.com'
                },
                {
                    name: 'youtube',
                    link: 'www.youtube.com'
                },
                {
                    name: 'twitter',
                    link: 'www.twitter.com'
                }
            ]
        }
    }
}
</script>

<style lang="scss">
@import '@/styles/variables.scss';

    .hero-container {
        position: relative;
        padding: $spacing * 10;
        padding-bottom: 0;
        overflow: hidden;

        img {
            position: absolute;
            top: 0;
            right: 0;
            width: 70%;
            transform: translate(20%, -15%);
            z-index: 0;
        }
    }

    .hero-content {
        width: 40%;

        h5 {
            letter-spacing: $spacing / 2.5;
            margin-bottom: $spacing * 2;
        }

        h1 {
            font-size: 60px;
            margin-bottom: $spacing * 3;
        }

        .green-divider {
            width: 30%;
            display: flex;
            gap: $spacing;
            margin-bottom: $spacing * 4;

            * {
                min-height: $spacing * .7;
                background: get-values($colors, 'gradients', 'green');
                border-radius: 20px;
            }

            .left-divider {
                width: $spacing * 2;
            }

            .right-divider {
                width: $spacing * 5;
            }
        }

        p {
            color: get-values($colors, 'text', 'grey-1');
            margin-bottom: $spacing * 6;
        }

        button {
            margin-bottom: $spacing * 7;
        }

        .social-list {
            display: flex;
            gap: $spacing;
            margin-bottom: $spacing * 3;

            a {
                color: get-values($colors, 'text', 'grey-3');
            }
        }
    }
</style>