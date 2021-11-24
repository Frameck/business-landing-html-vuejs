<template>
    <main class="main-container">
        <!-- 1° section con 4 card -->
        <section class="section white-section">
            <div class="left-section">
                <SectionText :text="this.firstSectionText"></SectionText>
                <Button :text="'view all'" :type="'primary'"></Button>
            </div>

            <div class="right-section">
                <Card
                v-for="card in cardElements"
                :elements="card"
                :key="card.title">
                </Card>
            </div>
        </section>

        <!-- 2° section con overlay verde -->
        <section class="section grey-section">
            <div class="left-section">
                <div class="green-overlay">
                    <img src="@/assets/img/busy-architect-PYVKWM4-1024x872.jpg" alt="">
                </div>
                <img src="@/assets/img/businesswoman-analysing-document-P8WSNMC-1024x820.jpg" alt="">
            </div>

            <div class="right-section">
                <SectionText :text="this.secondSectionText"></SectionText>
                <Button :text="'read more'" :type="'primary'"></Button>
            </div>
        </section>

        <!-- 3° section con galleria immagini -->
        <section class="section white-section-2">
            <div class="top-section">
                <div class="green-divider">
                    <div class="left-divider"></div>
                    <div class="right-divider"></div>
                </div>
                <SectionText :text="this.thirdSectionText"></SectionText>
            </div>

            <div class="bottom-section">
                <div class="img-container">
                    <img :src="image" :alt="image" v-for="(image, i) in imageList" :key="`image_${i}`">
                </div>
                <Button :text="'read more'" :type="'primary'"></Button>
            </div>
        </section>

        <!-- 4° section -->
        <section class="section grey-section-2">
            <div class="top-section">
                <!-- <div class="green-overlay">
                    <img src="@/assets/img/busy-architect-PYVKWM4-1024x872.jpg" alt="">
                </div> -->
                <div class="big-card">
                    <SectionText :text="this.fourthSectionText"></SectionText>
                    <ul>
                        <li v-for="(item, i) in cardsLists.bigCard" :key="item + i">
                            <i class="fa fa-check" aria-hidden="true"></i>
                            {{ item }}
                        </li>
                    </ul>
                </div>
            </div>

            <div class="bottom-section">
                <SectionText :text="this.fifthSectionText"></SectionText>
                <div class="pricing-cards">
                    <PricingCard :text="pricingCards.designing" :type="'secondary'"></PricingCard>
                    <PricingCard :text="pricingCards.development" :type="'primary'"></PricingCard>
                    <PricingCard :text="pricingCards.seo" :type="'secondary'"></PricingCard>
                </div>
            </div>
        </section>
    </main>
</template>

<script>
import SectionText from './SectionText.vue'
import Card from './Card.vue'
import Button from './Button.vue'
import PricingCard from './PricingCard.vue'

export default {
    name: 'Main',
    components: { SectionText, Card, Button, PricingCard },
    data() {
        return {
            firstSectionText: {
                subtitle: '',
                title: 'We Are Here To Make Your Website Look More Elegant And Stylish',
                text: ''
            },
            secondSectionText: {
                subtitle: '',
                title: 'learn more about our missions',
                text: 'Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. Separated they live in Bookmarksgrove right at the coast of the Semantics, a large language ocean. Separated they live in Bookmarksgrove.'
            },
            thirdSectionText: {
                subtitle: '',
                title: 'Our recent web designs & some examples of past projects',
                text: 'Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. Separated they live in Bookmarksgrove right at the coast of the Semantics, a large language ocean. Separated they live in Bookmarksgrove. Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts.'
            },
            fourthSectionText: {
                subtitle: '',
                title: 'We Love What We Do',
                text: 'Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. Separated they live in Bookmarksgrove right at the coast of the Semantics, a large language ocean. Separated they live in Bookmarksgrove. Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts.'
            },
            fifthSectionText: {
                subtitle: '',
                title: 'With Live Chat 24/7 Support',
                text: 'Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. Separated they live in Bookmarksgrove right at the coast of the Semantics, a large language ocean. Separated they live in Bookmarksgrove.'
            },
            cardsLists: {
                bigCard: [
                    'Far far away, behind the word mountains', 'far from the countries Vokalia and Consonantia', 'there live the blind texts'
                ]
            },
            pricingCards: {
                designing: {
                    title: 'designing',
                    subtitle: 'All Designs',
                    type: 'Design',
                    price: '13',
                    list: [ 'Creative Design Enabled', 'Vibrant Color Usage', 'Eye Catching Design', 'Extreme Typography', 'Exceptional Design' ]
                },
                development: {
                    title: 'development',
                    subtitle: 'Wordpress Projects',
                    type: 'Project',
                    price: '15',
                    list: [ 'Creative Design Enabled', 'Vibrant Color Usage', 'Eye Catching Design', 'Extreme Typography', 'Exceptional Design' ]
                },
                seo: {
                    title: 'seo',
                    subtitle: 'Web Products',
                    type: 'Product',
                    price: '10',
                    list: [ 'Creative Design Enabled', 'Vibrant Color Usage', 'Eye Catching Design', 'Extreme Typography', 'Exceptional Design' ]
                }
            },
            cardElements: [
                {
                    icon: 'fa fa-tachometer',
                    title: 'Speed Optimization',
                    subtitle: 'Far far away, behind the word mountains, far from the countries Vokalia...'
                },
                {
                    icon: 'fa fa-cloud',
                    title: 'Cloud Solutions',
                    subtitle: 'Far far away, behind the word mountains, far from the countries Vokalia...'
                },
                {
                    icon: 'fa fa-mobile',
                    title: 'Website Design',
                    subtitle: 'Far far away, behind the word mountains, far from the countries Vokalia...'
                },
                {
                    icon: 'fa fa-clock-o',
                    title: 'Online Marketing',
                    subtitle: 'Far far away, behind the word mountains, far from the countries Vokalia...'
                }
            ],
            imageList: [
                'require(@/assets/img/ina-soulis-227104-unsplash-1024x1024.jpg)',
                'require(@/assets/img/sunisa-misa-531163-unsplash-1024x1024.jpg)',
                'require(@/assets/img/355H-1024x1024.jpg)',
                'require(@/assets/img/photo-1448932252197-d19750584e56-1024x1024.jpg)',
                'require(@/assets/img/business-competition-PB366D8-1024x1024.jpg)',
                'require(@/assets/img/cozy-sofa-in-living-room-PQR5AB9-1024x1024.jpg)',
                'require(@/assets/img/aa9a4539-PQGJ7HU-1024x1024.jpg)',
                'require(@/assets/img/cody-davis-253928-unsplash-1024x1024.jpg)',
            ]
        }
    }
}
</script>

<style lang="scss">
@import '@/styles/variables.scss';

    .section {
        display: flex;
        justify-content: space-between;
        gap: $spacing * 10;
        padding-top: $spacing * 15;
        padding-bottom: $spacing * 15;
    }

    .white-section {
        .left-section {
            width: 35%;

            h1 {
                font-size: 50px;
            }
        }

        .right-section {
            width: calc(100% - 35% - ($spacing * 10));
            display: flex;
            flex-wrap: wrap;
            gap: $spacing * 3;
            justify-content: space-evenly;
        }
    }

    .grey-section {
        background-color: get-values($colors, 'bg', 'whitesmoke');

        img {
            width: 300px !important;
        }

        .left-section {
            width: calc(100% - 35% - ($spacing * 10));

            h1 {
                font-size: 50px;
            }

            .green-overlay {
                width: 75%;
                border-radius: 20px;
                position: relative;

                &::after {
                    position: absolute;
                    top: 0;
                    left: 0;
                    width: 100%;
                    height: 100%;
                    background: get-values($colors, 'gradients', 'green');
                }

                img {
                    width: 100%;
                    height: 100%;
                }
            }

            img {
                border-radius: 20px;
                box-shadow: 0 5px 15px rgb(0 0 0 / 0.2);

                // &:nth-of-type(1) {
                //     width: 75%;


                // }

                // &:nth-of-type(2) {
                //     width: 70%;
                // }
            }
        }

        .right-section {
            width: 35%;
        }
    }

    .white-section-2 {
        flex-direction: column;

        .top-section {
            position: relative;

            h1 {
                width: 45%;
                font-size: 50px;
            }

            p {
                width: calc(100% - 45%);
                position: absolute;
                bottom: 0;
                right: 0;
            }
        }

        .bottom-section {
            text-align: center;

            .img-container {
                display: flex;
                flex-wrap: wrap;
                gap: 10px;
                justify-content: space-between;
                margin-bottom: $spacing * 8;

                img {
                    flex-basis: calc(100% / 4 - 10px);
                    aspect-ratio: 1 / 1;
                }
            }
        }
    }

    .grey-section-2 {
        background-color: get-values($colors, 'bg', 'whitesmoke');
        flex-direction: column;

        .top-section {
            margin-bottom: $spacing * 10;
            width: 100%;

            .big-card {
                border-radius: 20px;
                background-color: get-values($colors, 'global', 'white');
                //height: 200px;
                width: 800px;
                padding: ($spacing * 10) ($spacing * 8);
    
                h1 {
                    font-size: 50px;
                }
    
                li {
                    color: get-values($colors, 'text', 'grey-1');
                    padding: $spacing 0;
    
                    i {
                        color: get-values($colors, 'global', 'green');
                        margin-right: $spacing / 2;
                    }
                }
            }
        }

        .bottom-section {
            display: flex;
            gap: $spacing * 4;

            .sectiontext-container {
                width: 30%;
            }

            .pricing-cards {
                width: calc(100% - 30% - ($spacing * 4));
                display: flex;
                gap: $spacing * 3;
            }
        }
    }

</style>