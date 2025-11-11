<script setup>
import { ref } from 'vue'

const isExpanded = ref(false)
</script>

<template>
    <div class="roar-image">
        <img src="../assets/image/odense_store.webp" alt="billede af odenses butikfacade" />
    </div>
    <div class="about-section">
        <h2>BUTIKKEN I ODENSE</h2>
        <div class="about-content">
            <!-- Dynamic class binding -->
            <p :class="{ collapsed: !isExpanded }">
                Faraos Cigarer i Odense bliver den første butik, der samler det bedste fra Faraos Cigarer i én butik.
                <br><br>
                Butikken, der åbnede 1. juni 2019, indeholder rollespil, live rollespil, brætspil, figurspil,
                tegneserier, Magic the Gathering, Warhammer, merchandise og meget, meget, MEGET mere.
                <br><br>
                Den 600 m2 store butik har også et stort spilareal, der giver mulighed for at spille både i butikkens
                almindelige åbningstider og ved butikkens mange hobbyaftner.
                <br><br>
                Tidligere har vores lokalet også huset vores airsoftbutik, men de har nu fået deres egne lokaler. Læs
                mere om det her:
            </p>
            <button class="read-more-btn" @click="isExpanded = !isExpanded">
                <!-- Her bruger vi en ternary operator som lader os skrive en if else statement i vores abstraction -->
                <!-- Basically hvis isExpanded er true vis "læs mindre", hvis false vis "læs mere" -->
                {{ isExpanded ? 'Læs mindre' : 'Læs Mere' }}
            </button>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@import '../assets/main.scss';

.about-section {
    margin: 2rem;
    padding: 2rem;
    background-color: $color-pharaos-gold;

    h2 {
        margin: 0;
        padding: 0;
        padding-bottom: 1.5rem;
    }
}

.about-content {
    position: relative;
}

.about-section h2 {
    color: white;
}

.about-content p {
    transition: max-height 0.3s ease;
    overflow: hidden;
}

.about-content p.collapsed {
    max-height: 7.3rem;
    position: relative;
}

.read-more-btn {
    background: none;
    border: none;
    color: #3396E6;
    cursor: pointer;
    padding: 0;
    font-size: inherit;
    margin-top: 0.5rem;
}

.read-more-btn:hover {
    color: #a8d1f3;
}

.roar-image {
    padding: 2rem;
    padding-bottom: 0;
}

.roar-image img {
    display: block;
    height: auto;
    max-width: 100%;
}

p,
button {
    font-family: $font-play;
}
</style>