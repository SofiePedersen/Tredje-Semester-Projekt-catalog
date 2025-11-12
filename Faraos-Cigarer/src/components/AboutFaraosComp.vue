<script setup>
    import { ref } from 'vue'

    const isExpanded = ref(false)
</script>

<template>
    <div class="about-section" aria-label="Tekstboks omhandlende Faraos Cigarers opstart">
        <h2>LIDT OM FARAOS</h2>
        <div class="about-content" aria-label="Tekstboksen">
            <!-- Dynamic class binding -->
            <div :class="{ collapsed: !isExpanded }" aria-label="Teksten">
                <p>Faraos Cigarer i Odense bliver den første butik, der samler det bedste fra Faraos Cigarer i én butik.</p>
                <p>Butikken, der åbnede 1. juni 2019, indeholder rollespil, live rollespil, brætspil, figurspil, tegneserier, Magic the Gathering, Warhammer, merchandise og meget, meget, MEGET mere.</p>
                <p>Den 600 m2 store butik har også et stort spilareal, der giver mulighed for at spille både i butikkens almindelige åbningstider og ved butikkens mange hobbyaftner.</p>
                <p>Tidligere har vores lokalet også huset vores airsoftbutik, men de har nu fået deres egne lokaler.</p>
            </div>
            <button class="read-more-btn" @click="isExpanded = !isExpanded" aria-label="Knap der åbner og lukker for mere og mindre tekst">
                <!-- Her bruger vi en ternary operator som lader os skrive en if else statement i vores abstraction -->
                <!-- Basically hvis isExpanded er true vis "læs mindre", hvis false vis "læs mere" -->
                {{ isExpanded ? 'Læs mindre' : 'Læs Mere' }}
            </button>
        </div>
    </div>
    <div class="roar-image" aria-label="Billederamme">
        <img src="../assets/image/faraos-cigarer-roar.webp" alt="Dekorativt billede af en bil der kører hurtigt" aria-label="Billedet"/>
    </div>
</template>

<style lang="scss" scoped>
@import '../assets/main.scss';

.about-section {
    margin-top: 3rem;
    padding: 2rem;
    padding-top: 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background-color: $color-pharaos-gold;
}

.about-content {
    position: relative;
}

.about-section h2 {
    color: white;
}

.about-content div {
    transition: max-height 0.3s ease;
    overflow: hidden;
}

.about-content div.collapsed {
    max-height: 7.3rem;
    position: relative;
}

.about-content div p {
    margin-bottom: 1rem;
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
    color: #8acbff;
}

.roar-image {
    background-color: $color-pharaos-gold;
    padding: 2rem;
    padding-top: 0rem;
    display: flex;
    justify-content: center;
}

.roar-image img {
    display: block;
    height: auto;
    max-width: 100%;
}

p, button {
  font-family: $font-play;
}

</style>