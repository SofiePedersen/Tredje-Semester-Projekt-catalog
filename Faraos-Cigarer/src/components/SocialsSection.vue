<script setup>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { faTiktok } from "@fortawesome/free-brands-svg-icons";
import { faFacebook } from "@fortawesome/free-brands-svg-icons";
import { faInstagram } from "@fortawesome/free-brands-svg-icons";
import { faXTwitter } from "@fortawesome/free-brands-svg-icons";
</script>

<template>
  <div class="socials-section" aria-label="Følg os på sociale medier">
    <a class="socials-section__facebook" href="https://www.facebook.com/faraoscigarer" target="_blank"
      rel="noopener noreferrer" :aria-label="'Følg Faraos Cigarer på Facebook'">
      <FontAwesomeIcon :icon="faFacebook" />
      <p>FACEBOOK</p>
    </a>

    <a class="socials-section__instagram" href="https://www.instagram.com/faraoscigarer/" target="_blank"
      rel="noopener noreferrer" :aria-label="'Følg Faraos Cigarer på Instagram'">
      <FontAwesomeIcon :icon="faInstagram" />
      <p>INSTAGRAM</p>
    </a>

    <a class="socials-section__tiktok" href="https://www.tiktok.com/@faraoscigarer" target="_blank"
      rel="noopener noreferrer" :aria-label="'Følg Faraos Cigarer på TikTok'">
      <FontAwesomeIcon :icon="faTiktok" />
      <p>TIKTOK</p>
    </a>

    <a class="socials-section__twitter" href="https://x.com/FaraosCigarer" target="_blank" rel="noopener noreferrer"
      :aria-label="'Følg Faraos Cigarer på Twitter'">
      <FontAwesomeIcon :icon="faXTwitter" />
      <p>TWITTER</p>
    </a>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/main.scss";

.socials-section__facebook {
  width: 100%;
  height: 5rem;
  background-color: $color-anubis-black;
  color: $color-pharaos-gold;
  font-family: $font-boogaloo;
  font-size: 2.44rem;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
  text-decoration: none;
}

.socials-section__instagram {
  width: 100%;
  height: 5rem;
  background-color: $color-pharaos-gold;
  color: $color-newspaper-white;
  -webkit-text-stroke: 0.07rem $color-anubis-black;
  font-family: $font-boogaloo;
  font-size: 2.44rem;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
  text-decoration: none;
}

.socials-section__tiktok {
  width: 100%;
  height: 5rem;
  background-color: $color-anubis-black;
  color: $color-pharaos-gold;
  font-family: $font-boogaloo;
  font-size: 2.44rem;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
  text-decoration: none;
}

.socials-section__twitter {
  width: 100%;
  height: 5rem;
  background-color: $color-pharaos-gold;
  color: $color-newspaper-white;
  -webkit-text-stroke: 0.07rem $color-anubis-black;
  font-family: $font-boogaloo;
  font-size: 2.44rem;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
  text-decoration: none;
}

.socials-section__instagram :deep(svg),
.socials-section__twitter :deep(svg) {
  stroke: $color-anubis-black;
  stroke-width: 0.5rem;
}

@media (min-width: 601px) {
  .socials-section {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
  }

  .socials-section__facebook,
  .socials-section__instagram,
  .socials-section__tiktok,
  .socials-section__twitter {
    width: calc(50% - 0.5rem);
    font-size: 1.4rem;
  }

  .socials-section__facebook :deep(svg),
  .socials-section__instagram :deep(svg),
  .socials-section__tiktok :deep(svg),
  .socials-section__twitter :deep(svg) {
    width: 1.8rem;
    height: 1.8rem;
    margin-right: 0.5rem;
  }

  .socials-section__instagram :deep(svg),
  .socials-section__twitter :deep(svg) {
    stroke-width: 1.3rem;
  }
}
</style>