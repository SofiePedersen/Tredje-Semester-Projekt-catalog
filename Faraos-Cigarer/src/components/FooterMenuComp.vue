<script setup>
import { ref } from 'vue';

const props = defineProps({
    title: {
        type: String,
        required: true
    },
    menuItems: {
        type: Array,
        required: true
    }
});

const isOpen = ref(false);

const toggleMenu = () => {
    isOpen.value = !isOpen.value;
};
</script>

<template>
    <div class="footer-lists" aria-label="Fold-ud menu">
        <div class="footer-lists--toggle" @click="toggleMenu" aria-label="Open og luk for fold-ud menuen">
            <h3>{{ title }}</h3>
            <img src="../assets/icons/arrow-vector-icon.svg" alt="ikon af en knap som er toggle"
                :class="{ 'rotated': isOpen }" />
        </div>
        <ul class="footer-lists__menu" :style="{ display: isOpen ? 'block' : 'none' }"
            aria-label="fold-ud menuer i footeren">
            <li v-for="(item, index) in menuItems" :key="index">
                <RouterLink class="footer-lists__menu--links" :to="item.link"
                    aria-label="Linker til andre sider på hjemmesiden.">
                    {{ item.text }}
                </RouterLink>
            </li>
        </ul>
    </div>
</template>

<style lang="scss" scoped>
@import '../assets/main.scss';

.footer-lists {
    border-top: solid 1px #2A2A2A;
    border-bottom: solid 1px #2A2A2A;

    .footer-lists--toggle {
        display: flex;
        padding: 1rem 2rem;
        justify-content: space-between;
        cursor: pointer;

        h3 {
            font-family: $font-boogaloo;
            color: $color-newspaper-white;
            font-size: 2rem;
            letter-spacing: 1.5px;
            margin: 0;
        }

        img {
            transform: rotate(180deg);
            transition: transform 0.3s ease;
        }

        img.rotated {
            transform: rotate(0deg);
        }
    }

    .footer-lists__menu {
        padding: 1rem 2rem;

        li {
            margin-bottom: 1rem;

            .footer-lists__menu--links {
                text-decoration: none;
                font-family: $font-play;
                color: $color-newspaper-white;
                font-size: 1.3rem;
            }

            .footer-lists__menu--links:hover {
                color: $color-tactical-blue;
            }
        }

        li:last-child {
            margin-bottom: 0rem;
        }
    }
}

@media (min-width: 1201px) {
    .footer-lists {
        border: none;
    }
    
    .footer-lists:first-of-type {
        padding-left: 15rem;
    }

    .footer-lists:nth-child(4) {
        padding-right: 15rem;
    }

    .footer-lists .footer-lists--toggle {
        padding: 0;
        cursor: default;
        pointer-events: none;
        margin-top: 2rem;

        img {
            display: none; // Hide the arrow on desktop
        }

        h3 {
            margin-bottom: 1rem;
            font-size: 1.8rem;
        }
    }

    .footer-lists .footer-lists__menu {
        display: block !important; // Always show menu on desktop
        padding: 0rem 0rem;
    }

    .footer-lists .footer-lists__menu li .footer-lists__menu--links {
        font-size: 1.1rem;
    }
}
</style>