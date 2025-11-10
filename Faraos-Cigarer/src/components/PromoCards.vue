<script setup>
defineProps({
  image: String,
  title: String,
});
</script>

<template>
  <div class="promo-card">
    <div class="promo-card__image">
      <img :src="image" :alt="title" />
      <button>{{ title }}</button>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/main.scss";

.promo-card__image {
  position: relative;
  width: 100%;
  margin-bottom: 5%;
}

.promo-card img {
  width: 400px;
  height: auto;
  object-fit: cover;
  box-shadow: 0.44rem 0.44rem rgba(0, 0, 0, 0.25);
}

.promo-card button {
  position: absolute;
  bottom: -0.94rem;
  left: 50%;
  transform: translateX(-50%);
  padding: 0.5rem 1rem;
  background-color: $color-anubis-black;
  color: $color-pharaos-gold;
  font-family: $font-boogaloo;
  font-size: 2rem;
  border: none;
  cursor: pointer;
  box-shadow: 0.44rem 0.44rem rgba(0, 0, 0, 0.25);
  white-space: nowrap;
  width: auto;
}

.promo-card button:hover {
  background-color: $color-pharaos-gold;
  color: $color-anubis-black;
}
</style>
