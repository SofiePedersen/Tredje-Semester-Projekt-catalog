<script setup>
import Header from "./components/Header.vue";
import { RouterView } from "vue-router";
import Footer from "./components/Footer.vue";
import HeaderDesktop from "./components/HeaderDesktop.vue";
</script>

<template>
  <Header></Header>
  <HeaderDesktop />
  <RouterView />
  <Footer></Footer>
</template>

<style scoped></style>
