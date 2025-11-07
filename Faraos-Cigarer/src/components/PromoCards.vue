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

<style scoped>
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
  background-color: #0e0f11;
  color: #efd17a;
  font-family: "Boogaloo";
  border: none;
  padding: 0.5rem 1rem;
  cursor: pointer;
  transition: 0.2s;
}

.category-card button:hover {
  background-color: #efd17a;
  color: #0e0f11;
}
</style>
