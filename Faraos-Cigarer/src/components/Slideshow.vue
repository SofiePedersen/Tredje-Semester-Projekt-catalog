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
  <div class="slideshow" aria-label="1 ud af 6: karrusel">
    <div v-show="currentIndex === 0">
      <img
        src="../assets/image/mobil_slideshow_1.webp"
        alt="Asterix bøger"
        aria-label="1 ud af 6: reklamebillede Asterix bøger"
      />
    </div>
    <div v-show="currentIndex === 1" aria-label="2 ud af 6: karrusel">
      <img
        src="../assets/image/mobil_slideshow_2.webp"
        alt="Efterårs udsalg op til 80% rabat"
        aria-label="2 ud af 6: reklamebillede Efterårs udsalg op til 80% rabat"
      />
    </div>
    <div v-show="currentIndex === 2" aria-label="3 ud af 6: karrusel">
      <img
        src="../assets/image/mobil_slideshow_3.webp"
        alt="Drager og demoner er ude nu"
        aria-label="3 ud af 6: reklamebillede Drager og demoner er ude nu"
      />
    </div>
    <div v-show="currentIndex === 3" aria-label="4 ud af 6: karrusel">
      <img
        src="../assets/image/mobil_slideshow_4.webp"
        alt="One piece merchandise"
        aria-label="4 ud af 6: reklamebillede One piece merchandise"
      />
    </div>
    <div v-show="currentIndex === 4" aria-label="5 ud af 6: karrusel">
      <img
        src="../assets/image/mobil_slideshow_5.webp"
        alt="The walking dead bind 10 med med Dansk version ude nu"
        aria-label="5 ud af 6: reklamebillede af bogen The walking dead bind 10 med med Dansk version ude nu"
      />
    </div>
    <div v-show="currentIndex === 5" aria-label="6 ud af 6: karrusel">
      <img
        src="../assets/image/mobil_slideshow_6.webp"
        alt="Ensomme ulv - Flugten fra mørket ude nu"
        aria-label="6 ud af 6: reklamebillede af bogen Ensomme ulv - Flugten fra mørket ude nu"
      />
    </div>

    <div class="slideshow__firkanter" aria-label="Indikatorer">
      <button
        v-for="n in totalSlides"
        :key="n"
        @click="goToSlide(n - 1)"
        :class="{ active: currentIndex === n - 1 }"
      ></button>
    </div>

    <div class="slideshow__control-bar" aria-label="Kontrolpanel">
      <div class="slideshow__control-bar--controls" aria-label="Styreknapper">
        <button @click="nextSlide(-1)" aria-label="Forrige billede">
          <FontAwesomeIcon :icon="faAngleLeft" />
        </button>
        <button @click="togglePause" aria-label="Pause karrusel">
          <FontAwesomeIcon :icon="isPaused ? faPlay : faPause" />
        </button>
        <button @click="nextSlide(1)" aria-label="Næste billede">
          <FontAwesomeIcon :icon="faAngleRight" />
        </button>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/main.scss";
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

.slideshow__firkanter {
  display: flex;
  justify-content: flex-start;
  gap: 0.48rem;
  position: absolute;
  bottom: 3.75rem;
  left: 2rem;
  margin-top: 0;
}

.slideshow__firkanter button {
  width: 0.7rem;
  height: 0.7rem;
  background-color: $color-newspaper-white;
  border-color: #000000;
  border-width: 0.06rem;
  border-style: solid;
  cursor: pointer;
  transition: background-color 0.3s;
}

.slideshow__firkanter button.active {
  background-color: #000000;
}

.slideshow__control-bar--controls button {
  background-color: $color-pharaos-gold;
  color: #000000;
  border-color: $color-pharaos-gold;
  cursor: pointer;
  margin-right: 0.6rem;
  padding: 0.3rem 0.3rem;
  border: 1px solid $color-pharaos-gold;
}

.slideshow__control-bar {
  width: 100%;
  max-width: 600px;
  background-color: #000000;
  padding: 0.6rem 0 0.6rem 2rem;
  display: flex;
  justify-content: flex-start;
  box-sizing: border-box;
}
</style>
