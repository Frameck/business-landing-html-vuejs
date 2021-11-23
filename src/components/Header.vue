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

        <Navbar :navLinks="this.navLinks"></Navbar>

        <Hero :text="this.heroText"></Hero>
    </header>
</template>

<script>
import Navbar from './Navbar.vue'
import Hero from './Hero.vue'

export default {
    name: 'Header',
    components: { Navbar, Hero },
    data() {
        return {
            navLinks: [
                {
                    name: 'home',
                    link: '#'
                },
                {
                    name: 'about',
                    link: '#'
                },
                {
                    name: 'services',
                    link: '#'
                },
                {
                    name: 'showcase',
                    link: '#'
                },
                {
                    name: 'blog',
                    link: '#'
                },
                {
                    name: 'contact',
                    link: '#'
                }
            ],
            heroText: {
                subtitle: '17 years of experience',
                title: 'Focus on Your Business',
                text: 'Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. Separated they live in Bookmarksgrove right at the coast of the Semantics, a large language ocean. Separated they live in Bookmarksgrove.'
            }
        }
    }
}
</script>

<style lang="scss">
@import '@/styles/variables.scss';

    .header-container {
        margin-top: calc(($spacing * .7) * 2 + 18px);
        background-color: get-values($colors, 'bg', 'whitesmoke');

        .nav-secondary {
            background-color: get-values($colors, 'bg', 'grey-2');
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            padding-top: $spacing * .7;
            padding-bottom: $spacing * .7;
        }

        .phone-numbers,
        .social-icons {
            color: get-values($colors, 'global', 'white');

            * {
                margin-right: $spacing * 1.5;
            }
        }

        .sectiontext-container {
            h1 {
                font-size: 65px;
            }
        }
    }

</style>