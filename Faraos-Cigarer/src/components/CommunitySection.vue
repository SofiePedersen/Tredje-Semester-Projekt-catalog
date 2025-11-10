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
      <P>FARAOS ER E-MÆRKET</P>
      <img :src="Community2" alt="Hjemmesiden er e-mærket" />
    </div>
    <div class="community-section__news">
      <P>NYHEDER</P>
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
  height: 10rem;
  background-color: $color-pharaos-gold;
  background-image: url("../assets/image/community_1.webp");
  background-repeat: no-repeat;
}

.community-section__e-label {
  width: 100%;
  height: 10rem;
  background-color: $color-anubis-black;
}

.community-section__news {
  width: 100%;
  height: 10rem;
  background-color: $color-pharaos-gold;
  background-image: url("@/assets/image/community_3.webp");
  background-repeat: no-repeat;
}
</style>
