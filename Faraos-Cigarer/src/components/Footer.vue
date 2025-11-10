<script setup>
import FooterList from "../components/FooterMenuComp.vue";

const footerSections = [
    {
        title: "BUTIKKER",
        items: [
            { text: "Åbningstider", link: "#" },
            { text: "Lokationer", link: "#" },
            { text: "Faraos Cigarer Online", link: "#" },
            { text: "Aktiviteter", link: "#" },
            { text: "Kalender", link: "#" }
        ]
    },
    {
        title: "KUNDESERVICE",
        items: [
            { text: "Kontakt os", link: "#" },
            { text: "Fragt & levering", link: "#" },
            { text: "Betaling", link: "#" },
            { text: "Handelsbetingelser", link: "#" },
            { text: "Ofte stillede spørgsmål", link: "#" },
        ]
    },
    {
        title: "SERVICE",
        items: [
            { text: "Klub Faraos", link: "#" },
            { text: "Min profil", link: "#" },
            { text: "Min ønskeliste", link: "#" },
            { text: "Mine ordrer", link: "#" },
            { text: "Nyhedsbrev", link: "#" },
        ]
    },
    {
        title: "OM FARAOS",
        items: [
            { text: "Om os", link: "#" },
            { text: "Job & praktik", link: "#" },
            { text: "Konkurrencebetingelser", link: "#" },
            { text: "Forlaget Faraos", link: "#" },
            { text: "Signeringer i Faraos", link: "#" },
        ]
    },
];
</script>

<template>
    <footer>
        <FooterList v-for="(section, index) in footerSections" :key="index" :title="section.title"
            :menu-items="section.items" />
        <div class="footer-info--wrapper">
            <div class="footer-info">
                <img class="footer-info--img" src="../assets/icons/phone-icon.svg" alt="Et gult ikon af en telefon" />
                <p class="footer-info--text">33 32 22 11</p>
            </div>
            <div class="footer-info">
                <img class="footer-info--img" src="../assets/icons/mail-icon.svg" alt="Et gult ikon af en telefon" />
                <p class="footer-info--text">faraos@faraos.dk</p>
            </div>
            <div class="footer-info">
                <img class="footer-info--img" src="../assets/icons/location-icon.svg" alt="Et gult ikon af en telefon" />
                <p class="footer-info--text">Skindergade 27, 1159 København K</p>
            </div>
        </div>
    </footer>
</template>

<style lang="scss" scoped>
@import '../assets/main.scss';

footer {
    background-color: $color-anubis-black;
    width: 100%;
}

.footer-info--wrapper {
    display: flex;
    flex-direction: column;
    padding: 2rem;

    .footer-info {
        display: flex;
        align-items: center;
        margin-bottom: 1rem;

        .footer-info--img {
            width: 2rem;
            margin-right: 2rem;
        }

        .footer-info--text {
            color: $color-newspaper-white;
            font-family: $font-play;
            font-size: 1rem;
        }
    }

    .footer-info:nth-of-type(2) {
    .footer-info--text {
        text-decoration: underline;
    }}
}
</style>