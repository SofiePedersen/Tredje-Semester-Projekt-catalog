<script setup>
import Slideshow from "../components/Slideshow.vue";
import Promosection from "@/components/PromoSection.vue";
import CommunitySection from "@/components/CommunitySection.vue";
import SocialsSection from "@/components/SocialsSection.vue";
import OmFaraosComp from "@/components/AboutFaraosComp.vue";
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
    <SocialsSection />
    <OmFaraosComp />
  </main>
</template>

<style scoped>
@media (min-width: 601px) {
  .h2 {
    text-align: left;
  }
}
</style>
