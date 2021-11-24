<template>
    <footer class="footer-container">
        <div class="section-1">
            <a href="#home">
                <img src="@/assets/img/cropped-Group-39-2x.png" alt="footer_logo">
            </a>
            <p>While the lovely valley teems with vapour around me, and the meridiano sun strikes the upper surface of the impenetrable foliage of my trees. While the lovely vaaley teems with vapour around me.</p>
        </div>

        <div class="section-2">
            <SectionText :text="section2"></SectionText>
            <ul>
                <li v-for="link in footerLinks" :key="link.name">
                    <a :href="link.link">
                        {{ link.name }}
                    </a>
                </li>
            </ul>
        </div>

        <div class="section-3">
            <SectionText :text="section3"></SectionText>
            <span>Patricia C. Amedee 4401 Waldeck Street Grapevine Nashville, TX 76051 <br><br> info@yourdomain.com <br><br> +99 (0) 101 0000 888</span>
        </div>

        <div class="section-4">
            <SectionText :text="section4"></SectionText>
            <a href="https://www.googlemaps.com">
                <img src="@/assets/img/map.png" alt="location-map">
            </a>
        </div>
    </footer>
</template>

<script>
import SectionText from './SectionText.vue'

export default {
    name: 'Footer',
    components: { SectionText },
    data() {
        return {
            section2: {
                title: 'quick links',
                subtitle: '',
                text: ''
            },
            section3: {
                title: 'contact',
                subtitle: '',
                text: ''
            },
            section4: {
                title: 'location on map',
                subtitle: '',
                text: ''
            },
            footerLinks: [
                {
                    name: 'Careers',
                    link: '#carrers'
                },
                {
                    name: 'News',
                    link: '#news'
                },
                {
                    name: 'Terms of use',
                    link: '#termsofuse'
                },
                {
                    name: 'Privacy Projects',
                    link: '#privacyprojects'
                },
                {
                    name: 'About',
                    link: '#about'
                },
                {
                    name: 'Contact',
                    link: '#contact'
                },
            ]
        }
    }
}
</script>

<style lang="scss">
@import '@/styles/variables.scss';

    .footer-container {
        padding: $spacing * 7;
        display: flex;
        gap: $spacing * 2;
        justify-content: space-between;
        margin-bottom: $spacing * 4;

        [class*="section"] {
            width: 20%;

            .sectiontext-container {
                width: 100%;
            }
        }

        h1 {
            font-size: 20px;
            text-transform: uppercase;
        }

        .section-1 {
            p {
                margin-top: $spacing * 2;
                color: get-values($colors, 'text', 'grey-1');
            }
        }

        .section-2 {
            ul {
                text-align: center;

                li {
                    padding: $spacing / 3;
                }

                a {
                    color: get-values($colors, 'text', 'grey-1');
                }
            }
        }

        .section-3 {
            span {
                color: get-values($colors, 'text', 'grey-1');
            }
        }

        .section-4 {
            img {
                width: 120%;
            }
        }
    }
</style>