<script setup>
import Community1 from "@/assets/image/community_1.webp";
import Community2 from "@/assets/image/community_2.webp";
import Community3 from "@/assets/image/community_3.webp";
</script>

<template>
  <div class="community-section">
    <div class="community-section__klub-faraos">
      <p>KLUB FARAOS</p>
    </div>
    <div class="community-section__e-label">
      <p>FARAOS ER E-MÆRKET</p>
      <img :src="Community2" alt="Hjemmesiden er e-mærket" />
    </div>
    <div class="community-section__news">
      <p>NYHEDER</p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/main.scss";

.community-section {
  display: flex;
  flex-direction: column;
}

.community-section__klub-faraos {
  width: 100%;
  height: 11rem;
  background-color: $color-pharaos-gold;
  background-image: url("../assets/image/community_1.webp");
  background-repeat: no-repeat;
  background-size: 42%;
  background-position: 0 0.09rem;
  color: $color-newspaper-white;
  font-family: $font-boogaloo;
  -webkit-text-stroke: 0.1rem $color-anubis-black;
  font-size: 2.44rem;
  font-weight: 400;
  cursor: pointer;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.community-section__e-label {
  width: 100%;
  height: 11rem;
  background-color: $color-anubis-black;
  color: $color-pharaos-gold;
  font-family: $font-boogaloo;
  font-size: 2.44rem;
  cursor: pointer;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  gap: 1rem;
}

.community-section__news {
  width: 100%;
  height: 11rem;
  background-color: $color-pharaos-gold;
  background-image: url("@/assets/image/community_3.webp");
  background-repeat: no-repeat;
  background-position: 1rem center;
  color: $color-newspaper-white;
  font-family: $font-boogaloo;
  -webkit-text-stroke: 0.1rem $color-anubis-black;
  font-size: 2.44rem;
  font-weight: 400;
  cursor: pointer;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
