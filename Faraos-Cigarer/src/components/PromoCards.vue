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
.category-card {
  text-align: center;
}

.image-wrapper {
  position: relative;
  width: 100%;
}

.category-card img {
  width: 400px;
  height: auto;
  object-fit: cover;
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
  border: none;
  cursor: pointer;
}

.category-card button:hover {
  background-color: $color-pharaos-gold;
  color: $color-anubis-black;
}
</style>
