<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const currentIndex = ref(0);
const totalSlides = 6;
const isPaused = ref(false); // <-- Holder styr på pause
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

// Start automatisk interval
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
    <!-- Slides -->
    <div v-for="n in totalSlides" :key="n" v-show="currentIndex === n - 1">
      <img
        :src="`../assets/image/mobil_slideshow_${n}.webp`"
        :alt="`Billede ${n}`"
      />
    </div>

    <!-- Navigationsknapper -->
    <div class="controls">
      <button @click="nextSlide(-1)">&#8592;</button>
      <!-- Venstre pil -->
      <button @click="togglePause">
        {{ isPaused ? "▶️" : "⏸️" }}
        <!-- Play/Pause ikon -->
      </button>
      <button @click="nextSlide(1)">&#8594;</button>
      <!-- Højre pil -->
    </div>

    <!-- Dots -->
    <div class="dots">
      <button v-for="n in totalSlides" :key="n" @click="goToSlide(n - 1)">
        {{ n }}
      </button>
    </div>
  </div>
</template>
