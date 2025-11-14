<!-- <script setup>
import Community2 from "@/assets/image/community_2.webp";
import SocialsSection from "./SocialsSection.vue";
</script>

<template>
  <div class="community-section" aria-label="Fællesskab sektion">
    <div class="community-section__klub-faraos" aria-label="Klub Faraos knap">
      <p>KLUB FARAOS</p>
    </div>

    <div class="community-section__e-label" aria-label="E-mærket knap">
      <p>FARAOS ER E-MÆRKET</p>
      <img :src="Community2" alt="Hjemmesiden er e-mærket" aria-label="Hjemmesiden er e-mærket" />
    </div>

    <div class="community-section__news" aria-label="Nyheder knap">
      <p>NYHEDER</p>
    </div>

    <div>
      <SocialsSection />
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
  position: relative;
  width: 100%;
  height: 11rem;
  color: $color-newspaper-white;
  background-color: $color-pharaos-gold;
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
  overflow: hidden;
}

.community-section__klub-faraos::before {
  content: "";
  position: absolute;
  inset: 0;
  background-image: url("../assets/image/community_1.webp");
  background-repeat: no-repeat;
  background-size: 42%;
  background-position: 0 0.09rem;
  opacity: 0.25;
}

.community-section__klub-faraos p {
  position: relative;
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

@media (min-width: 601px) {
  .community-section {
    padding: 2rem;
    padding-top: 0rem;
    display: flex;
    flex-direction: row;
    justify-content: center;
    flex-wrap: wrap;
    column-gap: 1rem;
    row-gap: 1rem;
  }

  .community-section__klub-faraos,
  .community-section__news,
  .community-section__e-label {
    width: 48%;
    font-size: 2.2rem;
  }

  .community-section__e-label {
    font-size: 1.9rem;
  }

  .community-section__klub-faraos::before {
    content: "";
    position: absolute;
    inset: 0;
    background-image: url("../assets/image/community_1.webp");
    background-repeat: no-repeat;
    background-size: 65%;
    background-position: 0 0rem;
  }
}

@media (min-width: 1200px) {
  h2 {
    text-align: left;
    padding-left: 4rem;
  }
}
</style> -->

<script setup>
import Community2 from "@/assets/image/community_2.webp";
import SocialsSection from "./SocialsSection.vue";
</script>

<template>
  <div class="community-section" aria-label="Fællesskab sektion">
    <div class="community-section__klub-faraos" aria-label="Klub Faraos knap">
      <p>KLUB FARAOS</p>
    </div>

    <div class="community-section__e-label" aria-label="E-mærket knap">
      <p>FARAOS ER E-MÆRKET</p>
      <img :src="Community2" alt="Hjemmesiden er e-mærket" aria-label="Hjemmesiden er e-mærket" />
    </div>

    <div class="community-section__news" aria-label="Nyheder knap">
      <p>NYHEDER</p>
    </div>

    <div class="community-section__socials">
      <SocialsSection />
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
  position: relative;
  width: 100%;
  height: 11rem;
  color: $color-newspaper-white;
  background-color: $color-pharaos-gold;
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
  overflow: hidden;
}

.community-section__klub-faraos::before {
  content: "";
  position: absolute;
  inset: 0;
  background-image: url("../assets/image/community_1.webp");
  background-repeat: no-repeat;
  background-size: 42%;
  background-position: 0 0.09rem;
  opacity: 0.25;
}

.community-section__klub-faraos p {
  position: relative;
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

@media (min-width: 601px) {
  .community-section {
    padding: 2rem;
    padding-top: 0rem;
    display: flex;
    flex-direction: row;
    justify-content: center;
    flex-wrap: wrap;
    column-gap: 1rem;
    row-gap: 1rem;
  }

  .community-section__klub-faraos,
  .community-section__news,
  .community-section__e-label,
  .community-section__socials {
    width: calc(50% - 0.5rem);
    font-size: 2.2rem;
  }

  .community-section__e-label {
    font-size: 1.9rem;
  }

  .community-section__klub-faraos::before {
    content: "";
    position: absolute;
    inset: 0;
    background-image: url("../assets/image/community_1.webp");
    background-repeat: no-repeat;
    background-size: 65%;
    background-position: 0 0rem;
  }
}

@media (min-width: 1200px) {
    .community-section {
    padding: 14rem;
    padding-top: 0rem;
    padding-bottom: 4rem;
  }

  .community-section__e-label,
  .community-section__klub-faraos,
  .community-section__news,
  .community-section__socials {
    height: 14rem;
  }
}
</style>