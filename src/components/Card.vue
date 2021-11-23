<template>
    <div class="card-container">
        <i :class="elements.icon" aria-hidden="true"></i>
        <h3>{{ elements.title }}</h3>
        <p>{{ elements.subtitle }}</p>
    </div>
</template>

<script>
export default {
    name: 'Card',
    props: { elements: Object } // title, subtitle, icon
}
</script>

<style lang="scss">
@import '@/styles/variables.scss';

    .card-container {
        border-radius: 16px;
        padding: $spacing * 3;
        background-color: get-values($colors, 'bg', 'whitesmoke');
        width: 350px;
        height: 230px; // aspect-ratio: 2 / 3
        box-shadow: 0 5px 10px rgb(0 0 0 / 0.2);

        i {
            font-size: 50px;
            margin-bottom: $spacing * 3;
            color: get-values($colors, 'global', 'green');
        }

        h3 {
            font-size: 23px;
            margin-bottom: $spacing * 2;
            font-weight: 400;
        }

        p {
            font-size: 15px;
            color: get-values($colors, 'text', 'grey-1');
        }
    }

</style>