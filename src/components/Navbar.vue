<template>
    <nav class="navbar-container flex-space-between">
        <!-- logo -->
        <a href="#home">
            <img src="@/assets/img/cropped-Group-39-2x.png" alt="navbar_logo">
        </a>
        <!-- voci di menù popolate tramite props -->
        <ul class="flex-space-between">
            <li v-for="(item, i) in navLinks" :key="item.name + i">
                <a :href="item.link + item.name">
                    {{ item.name.toUpperCase() }}
                </a>
            </li>
        </ul>
        <div class="right-section">
            <Button :text="'purchase'" :type="'primary'"></Button>
            <i class="fa fa-search" aria-hidden="true"></i>
        </div>
    </nav>
</template>

<script>
import Button from './Button.vue'

export default {
    name: 'Navbar',
    props: { navLinks: Array },
    components: { Button }
}
</script>

<style lang="scss">
@import '@/styles/variables.scss';

    .navbar-container {
        width: 100%;
        align-items: center;
        padding: $spacing * 1.5;
        background-color: get-values($colors, 'global', 'white');

        img {
            width: 200px;
        }

        ul {
            gap: $spacing;

            a {
                padding: $spacing;
                color: get-values($colors, 'text', 'grey-1');
            }
        }

        .right-section {
            i {
                margin-left: $spacing * 2;
                color: get-values($colors, 'global', 'green');
            }
        }
    }
</style>