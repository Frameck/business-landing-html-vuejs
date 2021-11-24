<template>
    <div class="coloredcard-container" :class="`color-${type}`">
        <span class="subtitle">{{ text.subtitle }}</span>
        <h3>{{ text.title }}</h3>

        <div class="bottom-section">
            <Button :text="'start now'" :type="'secondary'" v-if="type === 'primary'"></Button>
            <input type="text" placeholder="Enter Your Email Address" v-if="type === 'secondary'">
        </div>
    </div>
</template>

<script>
import Button from './Button.vue'

export default {
    name: 'ColoredCard',
    components: { Button },
    props: { text: Object, type: String }
}
</script>

<style lang="scss">
@import '@/styles/variables.scss';

    .coloredcard-container {
        padding: $spacing * 7;
        border-radius: 20px;
        color: get-values($colors, 'global', 'white');
        text-align: center;
        width: calc(100% / 2);

        .subtitle {
            color: get-values($colors, 'global', 'white');
            opacity: .7;
        }

        h3 {
            font-size: 30px;
            margin-top: $spacing;
            margin-bottom: $spacing * 4;
        }

        input {
            opacity: .1;
            border-radius: 30px;
            width: 70%;
            padding: $spacing * 1.5;

            &::placeholder {
                color: get-values($colors, 'global', 'white');
                opacity: 1;
            }
        }
    }

    .color-primary {
        background: get-values($colors, 'gradients', 'greenReverse');
    }

    .color-secondary {
        background: get-values($colors, 'gradients', 'black');
    }
</style>