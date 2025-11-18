<script setup>
import FaraosLogo from "@/assets/image/Faraos-cigarer-logo-svg.svg";
</script>

<template>
  <header>
    <div class="header-logo">
      <img
        :src="FaraosLogo"
        alt="Bil som laver en lyd"
        aria-label="Billede af en bil med lyd-effekt"
      />
    </div>
  </header>
</template>

<style lang="scss" scoped>
@import "../assets/main.scss";
</style>
