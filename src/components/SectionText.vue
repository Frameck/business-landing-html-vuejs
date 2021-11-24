<template>
    <div class="sectiontext-container">
        <h5 v-if="text.subtitle !== ''">{{ text.subtitle.toUpperCase() }}</h5>
        <h1 v-if="text.title !== ''">{{ text.title }}</h1>
        <!-- <h1>{{ colorLastWord }}</h1> -->
        <div class="green-divider">
            <div class="left-divider"></div>
            <div class="right-divider"></div>
        </div>
        <p v-if="text.text !== ''">{{ text.text }}</p>
    </div>
</template>

<script>

export default {
    name: 'Hero',
    props: { text: Object },
    data() {
        return {}
    },
    computed: {
        colorLastWord() {
            const title = this.text.title
            let array = title.split(' ')
            let lastWord = array[array.length - 1]
            let newTitle = `${array.slice(0, array.length-1).join(' ')} <span class="text-green">${lastWord}</span>`
            return newTitle
        }
    }
}
</script>

<style lang="scss">
@import '@/styles/variables.scss';

    .sectiontext-container {
        // width: 40%;

        h5 {
            letter-spacing: $spacing / 2.5;
            margin-bottom: $spacing * 2;
        }

        h1 {
            margin-bottom: $spacing * 3;
        }

        p {
            color: get-values($colors, 'text', 'grey-1');
            margin-bottom: $spacing * 6;
            font-size: 15px;
        }
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
</style>