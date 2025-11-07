<script setup>
defineProps({
  image: String,
  title: String,
});
</script>

<template>
  <div class="category-card">
    <img :src="image" :alt="title" />
    <button>{{ title }}</button>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/main.scss";
.category-card {
  text-align: center;
}

.category-card img {
  width: 100%;
  height: auto;
  border-radius: 10px;
}

.category-card button {
  margin-top: 0.5rem;
  background-color: $color-anubis-black;
  color: $color-pharaos-gold;
  font-family: $font-boogaloo;
  border: none;
  padding: 0.5rem 1rem;
  cursor: pointer;
  transition: 0.2s;
}

.category-card button:hover {
  background-color: $color-pharaos-gold;
  color: $color-anubis-black;
}
</style>
