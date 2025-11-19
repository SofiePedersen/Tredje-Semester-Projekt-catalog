<script setup>
import { ref } from 'vue'

const isOpen = ref(false)

const toggleMenu = () => {
    isOpen.value = !isOpen.value
}

const allLists = {
    fruits: ["Apple", "Banana", "Cherry"],
    animals: ["Dog", "Cat", "Mouse"],
    colors: ["Red", "Green", "Blue"],
    vehicles: ["Car", "Bike", "Bus"],
    frameworks: ["Vue", "React", "Angular"]
}

const currentList = ref([])

const loadList = (category) => {
    currentList.value = allLists[category] || []
}

</script>

<template>
    <div class="megamenu-container">
        <button class="cat-button" :class="{ 'cat-button-open': isOpen }" @click="toggleMenu">
            KATEGORIER
            <img class="cat-arrow" src="../assets/icons/arrow-vector-icon.svg" alt="arrow"
                :class="{ 'cat-arrow-open': isOpen }" />
        </button>

        <div class="megamenu" :class="{ 'megamenu-open': isOpen }">
            <div class="category-buttons">
                <button @click="loadList('fruits')">Bøger & Tegneserier</button>
                <button @click="loadList('animals')">Retro</button>
                <button @click="loadList('colors')">Merchandise</button>
                <button @click="loadList('vehicles')">Spil</button>
                <button @click="loadList('frameworks')">Udklædning</button>
            </div>

            <div v-if="currentList.length === 0" class="shown-message">
                <h3 class="msg-title">Hvad er du på udkig efter?</h3>
                <p class="msg-text">Klik på kategorierne, til venstre for at finde lige netop det produkt du leder
                    efter!</p>
                <p class="msg-text"><span class="qoute-style">"You have the high ground now" - Faraos Cigarer</span></p>
            </div>

            <ul v-else>
                <li v-for="item in currentList" :key="item">{{ item }}</li>
            </ul>
        </div>
        <div class="decoration" :class="{ 'decoration-open': isOpen }"></div>
    </div>
</template>

<style lang="scss">
@import "../assets/main.scss";

.megamenu-container {
    position: relative;
    display: inline-block;

    .cat-button {
        background-color: $color-anubis-black;
        color: $color-newspaper-white;
        border: none;
        padding: 1rem;
        font-family: $font-boogaloo;
        font-size: 1rem;
        height: 3.1rem;
        cursor: pointer;
        display: inline-flex;
        align-items: center;
        gap: 1rem;
        transition: background-color 0.1s ease;
        box-shadow: 0.3rem 0.3rem rgba(0, 0, 0, 0.25);

    }

    .cat-button-open {
        background-color: #efd17a;
    }

    .cat-arrow {
        transform: rotate(180deg);
        transition: transform 0.3s ease;
    }

    .cat-arrow-open {
        transform: rotate(0deg);
    }

    .megamenu {
        position: absolute;
        top: 120%;
        width: 100vw;
        margin-left: -2rem;
        background-color: $color-pharaos-gold;
        transform: scaleY(0);
        transform-origin: top;
        transition: transform 0.3s ease;
        opacity: 0;
        z-index: 100;
        display: flex;
        gap: 1rem;

        .shown-message {
            margin: 2rem;
            margin-left: 0;
            background-color: $color-anubis-black;
            color: $color-newspaper-white;
        }

        .category-buttons {
            padding: 2rem;
            padding-right: 0;
            display: flex;
            flex-direction: column;
            width: 25%;
            gap: 1rem;
            
            button {
                box-shadow: 0.3rem 0.3rem rgba(0, 0, 0, 0.25);
                background-color: $color-anubis-black;
                color: $color-newspaper-white;
                padding: 1rem;
                font-family: $font-boogaloo;
                text-transform: uppercase;
                font-size: 1.2rem;
                border: none;
            }

            button:hover {
                background-color: $color-newspaper-white;
                color: $color-tactical-blue;
            }
        }

    }

    .megamenu-open {
        transform: scaleY(1);
        opacity: 1;
        box-shadow: 0rem 0.3rem rgba(0, 0, 0, 0.25);
    }

    .decoration {
        display: none;
        background-color: #efd17a;
        width: 8.9rem;
        height: 20rem;
        position: absolute;
        box-shadow: 0.3rem 0.3rem rgba(0, 0, 0, 0.25);
    }

    .decoration-open {
        display: block;
        transform: scaleY(1);
        transition: transform 0.1s ease;
    }
}
</style>
