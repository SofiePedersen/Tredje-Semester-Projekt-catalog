<script setup>
import { ref } from 'vue'
import comicIcon from '../assets/icons/comic-icon.svg'
import spikyIcon from '../assets/icons/spiky-icon.svg'
import animeIcon from '../assets/icons/anime-icon.svg'
import dvdIcon from '../assets/icons/dvd-icon.svg'
import bookIcon from '../assets/icons/book-icon.svg'


const isOpen = ref(false)

const toggleMenu = () => {
    isOpen.value = !isOpen.value
}

const allLists = {
    dkComics: {
        title: "DK TEGNESERIER",
        image: comicIcon,
        items: [
            { name: "TINTIN", route: "/#" },
            { name: "ASTERIX", route: "/#" },
            { name: "DISNEY", route: "/#" },
            { name: "SUPERHELTE", route: "/#" },
            { name: "DANSK MANGA", route: "/#" },
            { name: "GRAPHIC NOVEL", route: "/#" },
            { name: "HUGO PRATT", route: "/#" },
            { name: "PAKKETILBUD", route: "/#" },
            { name: "BØRNEBØGER", route: "/#" },
            { name: "A-Z", route: "/#" }
        ]
    },
    usComics: {
        title: "US TEGNESERIER",
        image: spikyIcon,
        items: [
            { name: "KALENDERE", route: "/#" },
            { name: "SPOTLIGHT", route: "/#" },
            { name: "GRAPHIC NOVELS", route: "/#" },
            { name: "MARVEL", route: "/#" },
            { name: "DC", route: "/#" },
            { name: "STAR WARS", route: "/#" },
            { name: "ART BOOKS", route: "/#" },
            { name: "HUMOR", route: "/#" },
            { name: "DISNEY", route: "/#" },
            { name: "A-Z", route: "/#" }
        ]
    },
    manga: {
        title: "MANGA",
        image: animeIcon,
        items: [
            { name: "SPOTLIGHT", route: "/#" },
            { name: "YAOI", route: "/#" },
            { name: "YURI", route: "/#" },
            { name: "HENTAI", route: "/#" },
            { name: "ART BOOKS", route: "/#" },
            { name: "COOK BOOKS", route: "/#" },
            { name: "HOW TO DRAW MANGA", route: "/#" },
            { name: "LIGHT NOVELS", route: "/#" },
            { name: "ANIME", route: "/#" },
            { name: "MERCHANDISE", route: "/#" },
            { name: "A-Z", route: "/#" }
        ]
    },
    dvd: {
        title: "DVD & FILM",
        image: dvdIcon,
        items: [
            { name: "STUDIO GHIBLI", route: "/#" },
            { name: "ANIME", route: "/#" },
            { name: "TEGNEFILM", route: "/#" },
            { name: "SOUNDTRACK", route: "/#" },
            { name: "4K BLU-RAY", route: "/#" },
            { name: "BESKYTTELSE TIL DIN FILMSAMLING", route: "/#" },
            { name: "FILM & SERIER", route: "/#" },
            { name: "TINTIN", route: "/#" }
        ]
    },
    books: {
        title: "BØGER",
        image: bookIcon,
        items: [
            { name: "SPOTLIGHT", route: "/#" },
            { name: "KLASSIKERE", route: "/#" },
            { name: "GAVEIDEER", route: "/#" },
            { name: "STAR WARS", route: "/#" },
            { name: "WARHAMMER", route: "/#" },
            { name: "BØRNEBØGER", route: "/#" },
            { name: "BØGER PÅ DANSK", route: "/#" },
            { name: "A-Z", route: "/#" }
        ]
    }
}

const currentList = ref([])

const loadAllCategories = () => {
    currentList.value = Object.values(allLists)
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
                <button @click="loadList('books')">Bøger & Tegneserier</button>
                <button @click="loadList('animals')">Retro</button>
                <button @click="loadList('colors')">Merchandise</button>
                <button @click="loadList('vehicles')">Spil</button>
                <button @click="loadList('frameworks')">Udklædning</button>
            </div>

            <div v-if="!currentList" class="shown-message">
                <h3 class="msg-title">Hvad er du på udkig efter?</h3>
                <p class="msg-text">
                    Skal du vindues-shoppe, shop-amok eller bare smugkigge på alle vores mange
                    produkter? Så kan du klikke på kategorierne, til venstre for at finde lige netop det produkt du
                    leder efter!</p>
                <p class="msg-text"><span>"You have the high ground now" - Obi Wan Kenobi</span></p>
            </div>

            <div v-else class="category-content">
                <div class="category-wrapper">
                    <div class="category-header">
                        <img :src="currentList.image" alt="" class="category-image" />
                        <h2 class="category-title">{{ currentList.title }}</h2>
                    </div>

                    <div class="category-links">
                        <RouterLink v-for="item in currentList.items" :key="item.route" :to="item.route"
                            class="link-item">
                            {{ item.name }}
                        </RouterLink>
                    </div>
                </div>
            </div>
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
        background-color: $color-pharaos-gold;
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
            padding: 2rem;
            margin: 2rem;
            margin-left: 0;
            background-color: $color-anubis-black;
            color: $color-newspaper-white;

            .msg-title {
                font-family: $font-boogaloo;
                font-weight: normal;
                font-size: 3rem;
                color: $color-pharaos-gold;
                margin-bottom: 2rem;
            }

            .msg-text {
                color: $color-newspaper-white;
                font-size: 1.2rem;
                font-family: $font-play;

                span {
                    font-style: italic;
                    font-family: $font-play;
                    opacity: 0.5;
                }
            }

            .msg-text:last-of-type {
                margin-top: 1rem;
            }

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
        height: 2rem;
        position: absolute;
        box-shadow: 0.3rem 0.3rem rgba(0, 0, 0, 0.25);
    }

    .decoration-open {
        display: block;
        transform: scaleY(1);
        transition: transform 0.1s ease;
    }

    .category-content {
        padding: 2rem;
        padding-left: 0;
        display: flex;
        flex-wrap: wrap;
    }

    .category-header {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background-color: red;
        padding: 0.5rem;

        .category-image {
            width: 5rem;
            height: 5rem;
        }

        .category-title {
            padding: 0;
            margin: 0;
            font-size: 1.5rem;
            -webkit-text-stroke: 0;
            font-family: $font-boogaloo;
        }
    }

    .category-links {
        margin-top: 1.5rem;
        display: flex;
        flex-direction: column;
        gap: .5rem;

        .link-item {
            color: $color-anubis-black;
            font-size: 1.2rem;
            text-decoration: none;

            &:hover {
                text-decoration: underline;
            }
        }
    }

}
</style>
