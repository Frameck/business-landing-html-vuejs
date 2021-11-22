<template>
    <button :class="`btn-${type}`">
        <a :href="text.replaceAll(' ', '')">{{ text.toUpperCase() }}</a>
    </button>
</template>

<script>
export default {
    name: 'Button',
    props: { text: String, type: String }
}
</script>

<style lang="scss">
@import '@/styles/variables.scss';

    button {
        border: none;
        border-radius: 20px;
        // box-shadow: 3px 3px 100px 5px get-values($colors, 'global', 'green');
        padding: ($spacing * 1.3) ($spacing * 1.5);

        a {
            padding: ($spacing) ($spacing * 2);
            color: get-values($colors, 'global', 'white');
        }
    }

    .btn-primary {
        background: get-values($colors, 'gradients', 'green');
    }

    .btn-secondary {
        background: get-values($colors, 'gradients', 'black');
    }
</style>