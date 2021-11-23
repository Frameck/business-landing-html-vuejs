<template>
    <div class="hero-container">
        <div class="hero-content">
            <!-- <h5>{{ text.subtitle.toUpperCase() }}</h5>
            <h1>{{ text.title }}</h1>
            <h1>{{ colorLastWord }}</h1>
            <div class="green-divider">
                <div class="left-divider"></div>
                <div class="right-divider"></div>
            </div>
            <p>{{ text.text }}</p> -->

            <SectionText :text="text"></SectionText>

            <Button :text="'read more'" :type="'secondary'"></Button>

            <ul class="social-list">
                <li v-for="(social, i) in socialList" :key="social.name">
                    <a :href="social.link">{{ social.name.toUpperCase() }}</a>
                    <i class="fa fa-minus" aria-hidden="true" v-if="i < 3"></i>
                </li>
            </ul>
        </div>

        <img src="@/assets/img/Group-35-2x.png" alt="hero-image">
    </div>
</template>

<script>
import Button from './Button.vue'
import SectionText from './SectionText.vue'

export default {
    name: 'Hero',
    components: { Button, SectionText },
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

        .hero-content {
            width: 40%;
        }

        img {
            position: absolute;
            top: 0;
            right: 0;
            width: 70%;
            transform: translate(20%, -15%);
            z-index: 0;
        }

        button {
            margin-bottom: $spacing * 7;
        }
    }


    .social-list {
        display: flex;
        gap: $spacing;
        margin-bottom: $spacing * 3;

        li {
            display: flex;
            align-items: center;
        }

        a {
            color: get-values($colors, 'text', 'grey-3');

            &:not(:last-child) {
                margin-right: $spacing;
            }
        }

        i {
            font-size: 10px;
        }
    }
</style>