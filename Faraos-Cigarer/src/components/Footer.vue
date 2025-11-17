<script setup>
import FooterList from "../components/FooterMenuComp.vue";

const footerSections = [
    {
        title: "BUTIKKER",
        items: [
            { text: "Åbningstider", link: "/Butikker" },
            { text: "Lokationer", link: "/Butikker" },
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
        <div class="footer-info--wrapper" aria-label="Kontaktinformationer">
            <div class="footer-info" aria-label="Kontaktinformation">
                <img class="footer-info--img" src="../assets/icons/phone-icon.svg" alt="Et gult ikon af en telefon"
                    aria-label="kontaktikon" />
                <p class="footer-info--text" aria-label="kontaktinfo - telefon nummer">33 32 22 11</p>
            </div>
            <div class="footer-info" aria-label="Kontaktinformation">
                <img class="footer-info--img" src="../assets/icons/mail-icon.svg" alt="Et gult ikon af en telefon"
                    aria-label="kontaktikon" />
                <p class="footer-info--text" aria-label="kontaktinfo - mail">faraos@faraos.dk</p>
            </div>
            <div class="footer-info" aria-label="Kontaktinformation">
                <img class="footer-info--img" src="../assets/icons/location-icon.svg" alt="Et gult ikon af en telefon"
                    aria-label="kontaktikon" />
                <p class="footer-info--text" aria-label="kontaktinfo - adresse">Skindergade 27, 1159 København K</p>
            </div>
        </div>
        <div class="footer-logos" aria-label="Sociale medier informationer">
            <div class="footer-logos-wrapper" aria-label="sociale medier">
                <div class="footer-logos--rounded" aria-label="Facebook knap">
                    <a class="" href="https://www.facebook.com/faraoscigarer#" target="_blank"
                        rel="noopener noreferrer">
                        <img src="../assets/icons/facebook-icon.svg" alt="ikon af facebooks logo" />
                    </a>
                </div>
                <div class="footer-logos--rounded" aria-label="Instagram knap">
                    <a href="https://www.instagram.com/faraoscigarer/" target="_blank" rel="noopener noreferrer">
                        <img src="../assets/icons/instagram-icon.svg" alt="ikon af instagrams logo" />
                    </a>
                </div>
                <div class="footer-logos--rounded" aria-label="Tiktok knap">
                    <a href="https://www.tiktok.com/@faraoscigarer" target="_blank" rel="noopener noreferrer">
                        <img src="../assets/icons/tiktok-icon.svg" alt="ikon af tiktoks logo" />
                    </a>
                </div>
                <div class="footer-logos--rounded" aria-label="Twitter / X knap">
                    <a href="https://x.com/FaraosCigarer" target="_blank" rel="noopener noreferrer">
                        <img src="../assets/icons/twitter-x-icon.svg" alt="ikon af twitter logo" />
                    </a>
                </div>
            </div>
        </div>
        <div class="footer-payments" aria-label="betalingsmetoder">
            <p class="footer-payments--text" aria-label="Godkendt af e-handelsfonden">Godkendt af e-handelsfonden</p>
            <div class="footer-payments--img-wrapper">
                <img class="footer-payments--img" src="../assets/icons/master-card-icon.svg"
                    alt="Et ikon af mastercards logo" aria-label="Mastercard ikon" />
                <img class="footer-payments--img" src="../assets/icons/visa-icon.svg" alt="Et ikon af visas logo"
                    aria-label="Visa ikon" />
                <img class="footer-payments--img" src="../assets/icons/visa-elec-icon.svg"
                    alt="Et ikon af Visa Electronics logo" aria-label="Visa Electronic ikon" />
                <img class="footer-payments--img" src="../assets/icons/dk-icon.svg" alt="Et ikon af dankorts logo"
                    aria-label="Dankort ikon" />
                <img class="footer-payments--img" src="../assets/icons/faktura-icon.svg" alt="Et ikon af Fakturas logo"
                    aria-label="Faktura ikon" />
            </div>
            <a href="" class="footer--text" aria-label="Link til trustpilot">Gå til Trustpilot</a>
            <p class="footer--text" aria-label="Faraos Cigarer CVR: 17272241">© Faraos Cigarer Aps Cvr 17272241
            </p>
        </div>
        <div class="desktop-information" aria-label="Informationsbjælke til desktop">
            <p>© Faraos Cigarer Aps Cvr 17272241</p>
            <div class="footer-info" aria-label="Kontaktinformation">
                <img class="footer-info--img" src="../assets/icons/phone-icon.svg" alt="Et gult ikon af en telefon"
                    aria-label="kontaktikon" />
                <p class="footer-info--text" aria-label="kontaktinfo - telefon nummer">33 32 22 11</p>
            </div>
            <div class="footer-info" aria-label="Kontaktinformation">
                <img class="footer-info--img" src="../assets/icons/mail-icon.svg" alt="Et gult ikon af en mail"
                    aria-label="kontaktikon" />
                <p class="footer-info--text" aria-label="kontaktinfo - mail">faraos@faraos.dk</p>
            </div>
            <div class="footer-info" aria-label="Kontaktinformation">
                <img class="footer-info--img" src="../assets/icons/location-icon.svg" alt="Et gult ikon af en lokation"
                    aria-label="kontaktikon" />
                <p class="footer-info--text" aria-label="kontaktinfo - adresse">Skindergade 27, 1159 København K</p>
            </div>
            <a>Gå til Trustpilot</a>
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

        .footer-payments--text,
        .footer--text {
            color: $color-newspaper-white;
            font-family: $font-play;
            font-size: 1rem;
            text-decoration: none;
        }

        .footer-payements--text a:hover {
            color: $color-tactical-blue;
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

    .desktop-information {
        display: none; // Hide on mobile by default
    }

    // Desktop layout - horizontal menus
    @media (min-width: 1201px) {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        max-width: 100%;

        .footer-info--wrapper {
            display: none; // Hide contact info on desktop
        }

        .footer-logos {
            display: none; // Hide social media icons on desktop
        }

        .footer--text {
            display: none;
        }

        .footer-payments {
            width: 100%;
            padding-top: 2rem;
            padding-left: 15rem;
            padding-bottom: 0.9rem;
            border-top: none;
            align-items: flex-start; // Align to the left
        }

        .desktop-information {
            display: flex;
            justify-content: space-between;
            align-items: center;
            width: 100%;
            padding: 1.5rem 15rem;
            padding-top: 0rem;

            p, a {
                color: $color-newspaper-white;
                font-family: $font-play;
                font-size: 0.7rem;
                text-decoration: none;
                margin: 0;
            }

            a:hover {
                color: $color-tactical-blue;
            }

            .footer-info {
                display: flex;
                align-items: center;
                gap: 0.5rem;

                .footer-info--img {
                    width: 1.5rem;
                    height: 1.5rem;
                }

                .footer-info--text {
                    color: $color-newspaper-white;
                    font-family: $font-play;
                    font-size: 0.7rem;
                    margin: 0;
                }
            }
        }
    }
}
</style>