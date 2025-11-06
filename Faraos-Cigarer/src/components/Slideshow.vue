<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const currentIndex = ref(0);
const totalSlides = 6;
const isPaused = ref(false);
let interval = null;

// Skift til næste/forrige slide
function nextSlide(step = 1) {
  currentIndex.value = (currentIndex.value + step + totalSlides) % totalSlides;
}

// Skift direkte til et bestemt slide
function goToSlide(index) {
  currentIndex.value = index;
}

// Toggle pause/play
function togglePause() {
  isPaused.value = !isPaused.value;
  if (isPaused.value) {
    clearInterval(interval);
  } else {
    startInterval();
  }
}

function startInterval() {
  interval = setInterval(() => {
    nextSlide(1);
  }, 10000);
}

onMounted(() => {
  startInterval();
});

onUnmounted(() => {
  clearInterval(interval);
});
</script>

<template>
  <div class="slideshow">
    <div v-show="currentIndex === 0">
      <img src="../assets/image/mobil_slideshow_1.webp" alt="Billede 1" />
    </div>
    <div v-show="currentIndex === 1">
      <img src="../assets/image/mobil_slideshow_2.webp" alt="Billede 2" />
    </div>
    <div v-show="currentIndex === 2">
      <img src="../assets/image/mobil_slideshow_3.webp" alt="Billede 3" />
    </div>
    <div v-show="currentIndex === 3">
      <img src="../assets/image/mobil_slideshow_4.webp" alt="Billede 4" />
    </div>
    <div v-show="currentIndex === 4">
      <img src="../assets/image/mobil_slideshow_5.webp" alt="Billede 5" />
    </div>
    <div v-show="currentIndex === 5">
      <img src="../assets/image/mobil_slideshow_6.webp" alt="Billede 6" />
    </div>

    <div class="dots">
      <button @click="goToSlide(0)">1</button>
      <button @click="goToSlide(1)">2</button>
      <button @click="goToSlide(2)">3</button>
      <button @click="goToSlide(3)">4</button>
      <button @click="goToSlide(4)">5</button>
      <button @click="goToSlide(5)">6</button>
    </div>

    <div class="controls">
      <button @click="nextSlide(-1)">❮</button>
      <button @click="togglePause">
        {{ isPaused ? "▶️" : "⏸️" }}
      </button>
      <button @click="nextSlide(1)">❯</button>
    </div>
  </div>
</template>
