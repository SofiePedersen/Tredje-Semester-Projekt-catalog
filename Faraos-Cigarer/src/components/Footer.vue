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
                <img class="footer-info--img" src="../assets/icons/location-icon.svg"
                    alt="Et gult ikon af en telefon" />
                <p class="footer-info--text">Skindergade 27, 1159 København K</p>
            </div>
        </div>
        <div class="footer-logos">
            <div class="footer-logos-wrapper">
                <div class="footer-logos--rounded">
                    <a class="" href="https://www.facebook.com/faraoscigarer#" target="_blank"
                        rel="noopener noreferrer">
                        <img src="../assets/icons/facebook-icon.svg" alt="ikon af facebooks logo" />
                    </a>
                </div>
                <div class="footer-logos--rounded">
                    <a href="https://www.instagram.com/faraoscigarer/" target="_blank" rel="noopener noreferrer">
                        <img src="../assets/icons/instagram-icon.svg" alt="ikon af instagrams logo" />
                    </a>
                </div>
                <div class="footer-logos--rounded">
                    <a href="https://www.tiktok.com/@faraoscigarer" target="_blank" rel="noopener noreferrer">
                        <img src="../assets/icons/tiktok-icon.svg" alt="ikon af tiktoks logo" />
                    </a>
                </div>
                <div class="footer-logos--rounded">
                    <a href="https://www.facebook.com/faraoscigarer#" target="_blank" rel="noopener noreferrer">
                        <img src="../assets/icons/twitter-x-icon.svg" alt="ikon af twitter logo" />
                    </a>
                </div>
            </div>
        </div>
        <div class="footer-payments">
            <p class="footer-payments--text">Godkendt af e-handelsfonden</p>
            <div class="footer-payments--img-wrapper">
                <img class="footer-payments--img" src="../assets/icons/master-card-icon.svg"
                    alt="Et ikon af mastercards logo" />
                <img class="footer-payments--img" src="../assets/icons/visa-icon.svg" alt="Et ikon af visas logo" />
                <img class="footer-payments--img" src="../assets/icons/visa-elec-icon.svg"
                    alt="Et ikon af Visa Electronics logo" />
                <img class="footer-payments--img" src="../assets/icons/dk-icon.svg" alt="Et ikon af dankorts logo" />
                <img class="footer-payments--img" src="../assets/icons/faktura-icon.svg"
                    alt="Et ikon af Fakturas logo" />
            </div>
            <p class="footer-payments--text">Gå til Trustpilot</p>
            <p class="footer-payments--text">© Faraos Cigarer Aps Cvr 17272241</p>
        </div>
    </footer>
</template>

<style lang="scss" scoped>
@import '../assets/main.scss';

footer {
    background-color: $color-anubis-black;
    width: 100%;

    .footer-info--wrapper {
        display: flex;
        flex-direction: column;
        padding: 2rem;

        .footer-info {
            display: flex;
            align-items: center;
            margin-bottom: 1rem;

            .footer-info--img {
                width: 2.5rem;
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
            }
        }

        .footer-info:nth-of-type(3) {
            margin-bottom: 0;
        }
    }

    .footer-logos {
        display: flex;
        justify-content: center;
        padding: 2rem;
        padding-top: 0rem;

        .footer-logos-wrapper {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            width: 100%;

            .footer-logos--rounded {
                display: flex;
                justify-content: center;
                border-radius: 100rem;
                border: solid 2px $color-pharaos-gold;
                padding: 1rem;
                width: 2.5rem;
                height: 2.5rem;
            }
        }
    }

    .footer-payments {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;

        .footer-payments--text {
            color: $color-newspaper-white;
            font-family: $font-play;
            font-size: 1rem;
        }

        .footer-payments--text:nth-of-type(2),
        .footer-payments--text:nth-of-type(3) {
            margin: 1rem;
        }

        .footer-payments--text:nth-of-type(3) {
            margin-top: 0;
            margin-bottom: 2rem;
        }

        .footer-payments--img-wrapper {
            display: flex;
            justify-content: center;

            .footer-payments--img {
                margin: 0.5rem;
            }
        }


    }
}
</style>