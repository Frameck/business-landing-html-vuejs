<template>
    <div class="articlecard-container">
        <img :src="require('@/assets/img/' + text.img)" alt="">

        <div class="white-box">
            <span>{{ text.subtitle }}</span>
            <div class="title">
                <i class="fa fa-circle" aria-hidden="true"></i>
                <h4>{{ text.title }}</h4>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ArticleCard',
    props: { text: Object }
}
</script>

<style lang="scss">
@import '@/styles/variables.scss';

    .articlecard-container {
        position: relative;

        img {
            border-radius: 16px;
            box-shadow: 0 3px 7px rgb(0 0 0 / 0.2);
            width: 400px;
        }

        .white-box {
            position: absolute;
            bottom: 0;
            left: 0;
            transform: translate(12.5%, 30%);
            background-color: get-values($colors, 'global', 'white');
            box-shadow: 0 3px 7px rgb(0 0 0 / 0.2);
            border-radius: 10px;
            padding: ($spacing * 2.5) ($spacing * 2);
            width: 80%;

            span {
                color: get-values($colors, 'text', 'grey-1');
                font-size: 13px;
                opacity: .7;
                margin-left: $spacing * 2;
            }

            .title {
                display: flex;
                gap: $spacing;
                align-items: center;
            }

            i {
                vertical-align: middle;
                font-size: 10px;
                color: get-values($colors, 'global', 'green');
            }

            h4 {
                font-size: 18px;
                font-weight: 400;
            }
        }
    }
</style>