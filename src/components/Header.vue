<template>
    <header class="header-container">
        <nav class="nav-secondary flex-space-between">
            <div class="phone-numbers">
                <i class="fa fa-phone" aria-hidden="true"></i>
                <span>(001) 88451234</span>
                <span>88455438</span>
            </div>
            <div class="social-icons">
                <i class="fa fa-facebook" aria-hidden="true"></i>
                <i class="fa fa-twitter" aria-hidden="true"></i>
                <i class="fa fa-pinterest-p" aria-hidden="true"></i>
            </div>
        </nav>
        <Navbar></Navbar>
    </header>
</template>

<script>
import Navbar from './Navbar.vue'

export default {
    name: 'Header',
    components: { Navbar }
}
</script>

<style lang="scss">
@import '@/styles/variables.scss';

    .header-container {
        padding: $spacing * 2;
        margin-top: $spacing * 2;

        .nav-secondary {
            background-color: get-values($colors, 'bg', 'grey-2');
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
        }

        .phone-numbers,
        .social-icons {
            color: get-values($colors, 'global', 'white');

            * {
                margin-right: $spacing * 1.5;
            }
        }
    }

</style>