<script setup>
import { ref } from 'vue'

const isOpen = ref(false)

const toggleMenu = () => {
    isOpen.value = !isOpen.value
}
</script>

<template>
    <RouterLink class="button-wrapper" :class="{ 'button-wrapper-open': isOpen }" @click="toggleMenu" to="/#">
        <button id="megamenuBtn" class="cat-button" :class="{ 'cat-button-open': isOpen }">
            KATEGORIER
        </button>

        <img class="cat-arrow" src="../assets/icons/arrow-vector-icon.svg" alt="arrow"
            :class="{ 'cat-arrow-open': isOpen }" />
    </RouterLink>
</template>

<style lang="scss">
@import "../assets/main.scss";

.button-wrapper {
    background-color: $color-anubis-black;
    min-width: 6rem;
    box-shadow: 0.4rem 0.4rem rgba(0, 0, 0, 0.25);
    display: flex;
    justify-content: center;
    align-items: center;
    text-decoration: none;
}

.button-wrapper-open {
    background-color: #efd17a;
}

.cat-button {
    background-color: $color-anubis-black;
    padding: 1rem;
    border: none;
    color: $color-newspaper-white;
    font-family: $font-boogaloo;
    font-size: 1rem;
    padding-right: 0rem;
}

.cat-button-open {
    background-color: #efd17a;
    color: black;
}

.cat-arrow {
    transform: rotate(180deg);
    transition: transform 0.3s ease;
    padding: 1rem;
}

.cat-arrow-open {
    transform: rotate(0deg);    
}
</style>