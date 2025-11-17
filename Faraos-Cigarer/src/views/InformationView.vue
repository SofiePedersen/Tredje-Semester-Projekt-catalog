<script setup>
import InformationComp from "@/components/InformationComp.vue";
import ContactComponent from "@/components/ContactComponent.vue";
import InformationMap from "@/components/InformationMap.vue";
</script>

<template>
  <InformationMap />
  <h2 class="desktop_text">ÅBNINGSTIDER & KONTAKTINFORMATION</h2>
  <ContactComponent />
  <InformationComp />
</template>

<style lang="scss" scoped>
@import "../assets/main.scss";

.desktop_text {
  display: none;
}

@media (min-width: 601px) {
  .desktop_text {
    display: block;
  }
}
</style>
