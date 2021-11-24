<template>
    <div class="pricingcard-container">
        <h1>{{ text.title.toUpperCase() }}</h1>
        <span class="subtitle">{{ text.subtitle }}</span>
        <div :class="`${type}-bar`">
            <span>
                <span class="dollar">$ </span>
                <span class="price">{{ text.price }}</span>
                <span class="type"> /{{ text.type }}</span>
                <!-- $ {{ text.price }} /{{ text.type }} -->
            </span>
        </div>
        <ul>
            <li v-for="(item, i) in text.list" :key="item + i">
                <i class="fa fa-check" aria-hidden="true"></i>
                {{ item }}
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'PricingCard',
    props: { text: Object, type: String }
}
</script>

<style lang="scss">
@import '@/styles/variables.scss';

    .pricingcard-container {
        position: relative;
        border-radius: 16px;
        text-align: center;
        background-color: get-values($colors, 'global', 'white');
        padding: $spacing * 3;
        box-shadow: 0 3px 7px rgb(0 0 0 / 0.2);

        &::before {
            position: absolute;
            content: '';
            top: 0;
            left: 0;
            width: 100%;
            height: 16px;
            background: get-values($colors, 'gradients', 'black');
            border-top-left-radius: 16px;
            border-top-right-radius: 16px;
        }

        &:nth-child(2) {
            &::before {
                background: get-values($colors, 'gradients', 'green');
            }
        }

        h1 {
            font-size: 25px;
            margin-bottom: $spacing;
        }

        .subtitle {
            color: get-values($colors, 'text', 'grey-1');
        }

        ul {
            li {
                padding-top: $spacing;
                padding-bottom: $spacing;
            }
        }
        
        [class*="bar"] {
            padding-top: $spacing * 2;
            padding-bottom: $spacing * 2;
            margin-top: $spacing * 2;
            margin-bottom: $spacing * 3;
            display: flex;
            align-items: center;
            justify-content: center;

            span {
                color: get-values($colors, 'global', 'white');

                .dollar {
                    font-size: 19px;
                }

                .price {
                    font-size: 30px;
                }
            }
        }

        .primary-bar {
            background: get-values($colors, 'gradients', 'green');
        }

        .secondary-bar {
            background: get-values($colors, 'gradients', 'black');
        }
    }    

</style>