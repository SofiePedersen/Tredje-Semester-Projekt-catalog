<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const currentIndex = ref(0);
const totalSlides = 3;
let interval = null;

// Skift til næste/forrige slide
function nextSlide(step = 1) {
  currentIndex.value = (currentIndex.value + step + totalSlides) % totalSlides;
}

// Skift direkte til et bestemt slide
function goToSlide(index) {
  currentIndex.value = index;
}

// Automatisk skift hvert 5. sekund
onMounted(() => {
  interval = setInterval(() => {
    nextSlide(1);
  }, 5000);
});

onUnmounted(() => {
  clearInterval(interval);
});
</script>

<template>
  <div>
    <!-- Slide 1 -->
    <div v-show="currentIndex === 0">
      <img src="../assets/image/mobil_slideshow_1.webp" alt="Billede 1" />
    </div>

    <!-- Slide 2 -->
    <div v-show="currentIndex === 1">
      <img src="../assets/image/mobil_slideshow_2.webp" alt="Billede 2" />
    </div>

    <!-- Slide 3 -->
    <div v-show="currentIndex === 2">
      <img src="../assets/image/mobil_slideshow_3.webp" alt="Billede 3" />
    </div>

    <!-- Knapper -->
    <button @click="nextSlide(-1)">Forrige</button>
    <button @click="nextSlide(1)">Næste</button>

    <!-- Dots -->
    <div>
      <button @click="goToSlide(0)">1</button>
      <button @click="goToSlide(1)">2</button>
      <button @click="goToSlide(2)">3</button>
    </div>
  </div>
</template>
