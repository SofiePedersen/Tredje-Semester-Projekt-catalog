<script setup>
defineProps({
  image: String,
  title: String,
});
</script>

<template>
  <div class="category-card">
    <div class="image-wrapper">
      <img :src="image" :alt="title" />
      <button>{{ title }}</button>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/main.scss";

.image-wrapper {
  position: relative;
  width: 100%;
  margin-bottom: 5%;
}

.category-card img {
  width: 400px;
  height: auto;
  object-fit: cover;
  box-shadow: 7px 7px 2px rgba(0, 0, 0, 0.45);
}

.category-card button {
  position: absolute;
  bottom: -15px;
  left: 50%;
  transform: translateX(-50%);
  padding: 0.5rem 1rem;
  background-color: $color-anubis-black;
  color: $color-pharaos-gold;
  font-family: $font-boogaloo;
  font-size: 32px;
  border: none;
  cursor: pointer;
  box-shadow: 7px 7px 2px rgba(0, 0, 0, 0.45);
  white-space: nowrap;
  width: auto;
}

.category-card button:hover {
  background-color: $color-pharaos-gold;
  color: $color-anubis-black;
}
</style>
