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
                    <img :src="require('@/assets/img/' + image)" :alt="image" v-for="(image, i) in imageList" :key="`image_${i}`">
                </div>
                <Button :text="'read more'" :type="'primary'"></Button>
            </div>
        </section>

        <!-- 4° section -->
        <section class="section grey-section-2">
            <div class="top-section">
                <div class="green-overlay">
                    <div class="text">
                        <h3>280</h3>
                        <span>PROJECTS</span>
                        <div class="bottom-text">
                            <div class="left">
                                <h4>+3500</h4>
                                <span>USER'S COMMENTS</span>
                            </div>
                            <div class="right">
                                <h4>100%</h4>
                                <span>HAPPY CLIENTS</span>
                            </div>
                        </div>
                    </div>
                    <img src="@/assets/img/person-with-long-curly-hair-PZ99QM2-2x.jpg" alt="">
                </div>
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

        <!-- 5° section -->
        <section class="section">

        </section>

        <!-- 6° section -->
        <section class="section grey-section-3">
            <div class="top-section">
                <SectionText :text="this.sixthSectionText"></SectionText>
            </div>
            <div class="articles-container">
                <ArticleCard v-for="item in articleCard" :key="item.name" :text="item"></ArticleCard>
            </div>
            <div class="button">
                <Button :text="'view all post'" :type="'secondary'"></Button>
            </div>
            <div class="bottom-section">
                <div class="colored-cards">
                    <ColoredCard :text="coloredCards.firstCard" :type="'secondary'"></ColoredCard>
                    <ColoredCard :text="coloredCards.secondCard" :type="'primary'"></ColoredCard>
                </div>
                <div class="clients">
                    <img :src="require('@/assets/img/' + img)" alt="" v-for="img in clientsList" :key="img">
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
import ArticleCard from './ArticleCard.vue'
import ColoredCard from './ColoredCard.vue'

export default {
    name: 'Main',
    components: { SectionText, Card, Button, PricingCard, ArticleCard, ColoredCard },
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
            sixthSectionText: {
                subtitle: '',
                title: 'Latest News & Our Blog',
                text: ''
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
            coloredCards: {
                firstCard: {
                    title: 'Start a New Project',
                    subtitle: 'Are You Ready?'
                },
                secondCard: {
                    title: 'Let\'s Talk About You',
                    subtitle: 'What Are You Waiting for?'
                }
            },
            clientsList: [
                'client-1-2x.png',
                'client-9-2x.png',
                'client-7-2x.png',
                'client-3-2x.png',
                'client-4-2x.png',
                'client-5-2x.png',
            ],
            imageList: [
                'ina-soulis-227104-unsplash-1024x1024.jpg',
                'sunisa-misa-531163-unsplash-1024x1024.jpg',
                '355H-1024x1024.jpg',
                'photo-1448932252197-d19750584e56-1024x1024.jpg',
                'business-competition-PB366D8-1024x1024.jpg',
                'cozy-sofa-in-living-room-PQR5AB9-1024x1024.jpg',
                'aa9a4539-PQGJ7HU-1024x1024.jpg',
                'cody-davis-253928-unsplash-1024x1024.jpg',
            ],
            articleCard: [
                {
                    title: 'Marketing Ideas',
                    subtitle: ' May 24, 2018 by Alex',
                    img: 'serious-businesswoman-with-documents-talking-on-P9Q6LX6-1024.jpg'
                },
                {
                    title: 'Rest During Working Hours',
                    subtitle: ' May 24, 2018 by Alex',
                    img: 'Businessman-at-the-desk-in-his-office-resting--1024x768.jpg'
                },
                {
                    title: 'Develop your Startup Idea',
                    subtitle: ' May 24, 2018 by Alex',
                    img: 'simple-home-office-with-tree-PBXRXYB-large-1024x768.jpg'
                }
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
        position: relative;
        padding-bottom: $spacing * 30;

        .left-section {
            width: calc(100% - 35% - ($spacing * 10));
            position: relative;

            h1 {
                font-size: 50px;
            }

            .green-overlay {
                width: 90%;
                height: 100%;
                border-radius: 20px;
                position: absolute;
                top: 0;
                left: 0;
                overflow: hidden;

                img {
                    width: 100%;
                    height: 100%;
                }

                &::after {
                    position: absolute;
                    content: '';
                    top: 0;
                    left: 0;
                    width: 100%;
                    height: 100%;
                    background: get-values($colors, 'gradients', 'green');
                    opacity: .8;
                    border-radius: 20px;
                }
            }

            img {
                width: 75%;
                border-radius: 20px;
                box-shadow: 0 5px 15px rgb(0 0 0 / 0.2);
                position: absolute;
                z-index: 0;
                top: 50px;
                right: 20px;
            }
        }

        .right-section {
            width: 35%;

            h1 {
                font-size: 50px;
            }
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
                    width: calc(100% / 4 - 10px);
                    aspect-ratio: 1 / 1;
                }
            }
        }
    }

    .grey-section-2 {
        background-color: get-values($colors, 'bg', 'whitesmoke');
        flex-direction: column;
        position: relative;

        .top-section {
            margin-bottom: $spacing * 10;
            width: 100%;
            position: relative;
            height: 800px;

            .green-overlay {
                width: 60%;
                border-radius: 20px;
                position: absolute;
                top: 0;
                left: 0;
                overflow: hidden;

                img {
                    width: 100%;
                    height: 100%;
                }

                &::after {
                    position: absolute;
                    content: '';
                    top: 0;
                    left: 0;
                    width: 100%;
                    height: 100%;
                    background: get-values($colors, 'gradients', 'green');
                    opacity: .8;
                    border-radius: 20px;
                }

                .text {
                    color: get-values($colors, 'global', 'white');
                    position: absolute;
                    z-index: 1;
                    top: 50%;
                    left: 50%;
                    text-align: center;
                    transform: translate(-50%, -50%);

                    h3 {
                        font-size: 100px;
                        font-weight: 200;
                        margin-bottom: $spacing;
                    }

                    .bottom-text {
                        display: flex;
                        gap: $spacing * 5;
                        margin-top: $spacing * 8;

                        h4 {
                            font-size: 40px;
                            margin-bottom: $spacing;
                        }
                    }
                }
            }

            .big-card {
                border-radius: 20px;
                background-color: get-values($colors, 'global', 'white');
                width: 700px;
                padding: ($spacing * 10) ($spacing * 8);
                position: absolute;
                top: 70px;
                right: 0;
    
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

                h1 {
                    font-size: 50px;
                }
            }

            .pricing-cards {
                width: calc(100% - 30% - ($spacing * 4));
                display: flex;
                gap: $spacing * 3;
            }
        }
    }

    .grey-section-3 {
        flex-direction: column;
        position: relative;

        .top-section {
            display: flex;
            justify-content: center;

            h1 {
                font-size: 50px;
            }

            .green-divider {
                margin-left: $spacing * 20;
            }
        }

        .articles-container {
            display: flex;
            justify-content: space-evenly;
            gap: $spacing * 2;
        }

        .button {
            text-align: center;
        }

        .bottom-section {
            .colored-cards {
                display: flex;
                gap: $spacing * 3;
            }

            .clients {
                text-align: center;
                margin-top: $spacing * 5;

                img {
                    width: 80px;
                    margin-right: $spacing * 15;

                    &:last-child {
                        margin-right: 0;
                    }
                }
            }
        }
    }

</style>