<script setup>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { faPlay } from "@fortawesome/free-solid-svg-icons";
import { faPause } from "@fortawesome/free-solid-svg-icons";
import { faAngleLeft } from "@fortawesome/free-solid-svg-icons";
import { faAngleRight } from "@fortawesome/free-solid-svg-icons";
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
      <button
        v-for="n in totalSlides"
        :key="n"
        @click="goToSlide(n - 1)"
        :class="{ active: currentIndex === n - 1 }"
      ></button>
    </div>

    <div class="control-bar">
      <div class="controls">
        <button @click="nextSlide(-1)">
          <FontAwesomeIcon :icon="faAngleLeft" />
        </button>
        <button @click="togglePause">
          <FontAwesomeIcon :icon="isPaused ? faPlay : faPause" />
        </button>
        <button @click="nextSlide(1)">
          <FontAwesomeIcon :icon="faAngleRight" />
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.slideshow {
  position: relative;
  width: 100%;
  max-width: 600px;
  margin: 0 auto;
}

.slideshow img {
  width: 100%;
  display: block;
}

.dots {
  display: flex;
  justify-content: flex-start;
  gap: 8px;
  position: absolute;
  bottom: 50px;
  left: 25px;
  margin-top: 0;
}

.dots button {
  width: 12px;
  height: 12px;
  background-color: #ffffff;
  border-color: #000000;
  border-width: 1px;
  border-style: solid;
  cursor: pointer;
  transition: background-color 0.3s;
}

.dots button.active {
  background-color: #000000;
}

.controls button {
  background-color: #efd17a;
  color: #000000;
  border-color: #efd17a;
  cursor: pointer;
}

.control-bar {
  width: 100%;
  max-width: 600px;
  margin: 0 auto;
  background-color: #000000;
  padding: 10px 0 10px 40px;
  display: flex;
  justify-content: flex-start;
  box-sizing: border-box;
}
</style>
