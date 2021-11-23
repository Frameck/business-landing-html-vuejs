<template>
    <main class="main-container">
        <!-- 1° section con 4 card -->
        <div class="white-section">
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
        </div>
    </main>
</template>

<script>
import SectionText from './SectionText.vue'
import Card from './Card.vue'
import Button from './Button.vue'

export default {
    name: 'Main',
    components: { SectionText, Card, Button },
    data() {
        return {
            firstSectionText: {
                subtitle: '',
                title: 'We Are Here To Make Your Website Look More Elegant And Stylish',
                text: ''
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
            ]
        }
    }
}
</script>

<style lang="scss">
@import '@/styles/variables.scss';

    .white-section {
        display: flex;
        justify-content: space-between;
        gap: $spacing * 10;
        padding-top: $spacing * 15;
        padding-bottom: $spacing * 15;

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

</style>