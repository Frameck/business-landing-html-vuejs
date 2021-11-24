<template>
    <div id="app">
        <Header></Header>
        <Main></Main>
        <Footer></Footer>
        <nav class="nav-secondary-2 flex-space-between">
            <div class="phone-numbers">
                <i class="fa fa-copyright" aria-hidden="true"></i>
                <span>2020 PHILOX BUSINESS THEME</span>
            </div>
            <div class="social-icons">
                <i class="fa fa-facebook" aria-hidden="true"></i>
                <i class="fa fa-twitter" aria-hidden="true"></i>
                <i class="fa fa-pinterest-p" aria-hidden="true"></i>
            </div>
        </nav>
    </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import Footer from './components/Footer.vue'

export default {
    name: 'App',
    components: { Header, Main, Footer },
    data() {
        return {

        }
    }
}
</script>

<style lang="scss">
@import '@/styles/main.scss';

    .nav-secondary-2 {
        background-color: get-values($colors, 'bg', 'grey-2');
        position: absolute;
        left: 0;
        width: 100%;
        padding-top: $spacing * 3;
        padding-bottom: $spacing * 3;
    }

    .phone-numbers,
    .social-icons {
        color: get-values($colors, 'text', 'grey-1');

        * {
            margin-right: $spacing * 1.5;
        }
    }
</style>