<script setup>
import PromoCards from "./PromoCards.vue";
import Promo1 from "@/assets/image/promo_1.webp";
import Promo2 from "@/assets/image/promo_2.webp";
import Promo3 from "@/assets/image/promo_3.webp";

const categories = [
  {
    image: Promo1,
    title: "POPULÆRE PRODUKTER",
  },
  {
    image: Promo2,
    title: "NYE VARER",
  },
  {
    image: Promo3,
    title: "TILBUD",
  },
];
</script>

<template>
  <div class="promo-section" aria-label="Promoveringssektion">
    <PromoCards
      v-for="(item, index) in categories"
      :key="index"
      :image="item.image"
      :title="item.title"
    />
  </div>
</template>

<style scoped>
.promo-section {
  display: flex;
  gap: 1.5rem;
  justify-content: center;
  flex-wrap: wrap;
}

@media (min-width: 601px) {
  .promo-section {
    margin: 0 auto;
    display: flex;
    flex-wrap: nowrap;
    justify-content: space-between;
    padding-left: 2rem;
    padding-right: 2rem;
  }
}

@media (min-width: 1200px) {
  .promo-section {
    padding-left: 20rem;
    padding-right: 20rem;
  }
}
</style>
