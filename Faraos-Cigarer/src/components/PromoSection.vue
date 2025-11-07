<script setup>
import PromoCards from "./PromoCards.vue";
import placeholder from "@/assets/image/placeholder.webp";
import Promo1 from "@/assets/image/promo_1.webp";
import Promo2 from "@/assets/image/promo_2.webp";
import Promo3 from "@/assets/image/promo_3.webp";

const categories = [
  {
    image: Promo1,
    title: "Populære produkter",
  },
  {
    image: Promo2,
    title: "Nye varer",
  },
  {
    image: Promo3,
    title: "Tilbud",
  },
];
</script>

<template>
  <section class="category-section">
    <PromoCards
      v-for="(item, index) in categories"
      :key="index"
      :image="item.image"
      :title="item.title"
    />
  </section>
</template>

<style scoped>
.category-section {
  display: flex;
  gap: 1.5rem;
  justify-content: center;
  flex-wrap: wrap;
}
</style>
