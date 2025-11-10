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
    <div class="footer-lists">
        <div class="footer-lists--toggle" @click="toggleMenu">
            <h3>{{ title }}</h3>
            <img src="../assets/icons/arrow-vector-icon.svg" alt="ikon af en knap som er toggle" :class="{ 'rotated': isOpen }"
            >
        </div>
        <ul class="footer-lists__menu" :style="{ display: isOpen ? 'block' : 'none' }">
            <li v-for="(item, index) in menuItems" :key="index">
                <RouterLink class="footer-lists__menu--links" :to="item.link">
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
        display: flex;
        justify-content: space-between;
        cursor: pointer;

        h3 {
            font-family: $font-boogaloo;
            color: $color-newspaper-white;
            font-size: 1.5rem;
            letter-spacing: 1.5px;
        }

        img {
            transition: transform 0.3s ease;
        }

        img.rotated {
            transform: rotate(180deg);
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
        }

        li:last-child {
            margin-bottom: 0rem;
        }
    }
}
</style>