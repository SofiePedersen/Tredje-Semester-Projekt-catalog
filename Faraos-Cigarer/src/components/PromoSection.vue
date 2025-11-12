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
  <div class="promo-section">
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
</style>
