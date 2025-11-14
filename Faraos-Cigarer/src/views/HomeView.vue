<script setup>
import Slideshow from "../components/Slideshow.vue";
import Promosection from "@/components/PromoSection.vue";
import CommunitySection from "@/components/CommunitySection.vue";
import SocialsSection from "@/components/SocialsSection.vue";
import AboutFaraosComp from "@/components/AboutFaraosComp.vue";
import DesktopSlideshow from "@/components/DesktopSlideshow.vue";
</script>

<template>
  <main>
    <Slideshow />
    <DesktopSlideshow />
    <h2>UDFORSK FARAOS UNIVERS</h2>
    <Promosection />
    <h2>FARAOS FÆLLESKAB</h2>
    <CommunitySection />
    <AboutFaraosComp />
  </main>
</template>

<style scoped></style>
