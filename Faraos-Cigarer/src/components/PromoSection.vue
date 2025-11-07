<script setup>
import PromoCards from "./PromoCards.vue";
import placeholder from "@/assets/image/placeholder.webp";

const categories = [
  {
    image: placeholder,
    title: "Populære produkter",
  },
  {
    image: placeholder,
    title: "Nye varer",
  },
  {
    image: placeholder,
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
