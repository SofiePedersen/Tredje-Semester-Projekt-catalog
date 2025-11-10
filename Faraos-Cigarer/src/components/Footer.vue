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
    <FooterList 
      v-for="(section, index) in footerSections" 
      :key="index"
      :title="section.title"
      :menu-items="section.items"
    />
  </footer>
</template>
<style lang="scss" scoped>
@import '../assets/main.scss';

footer {
    background-color: $color-anubis-black;
    width: 100%;
}
</style>