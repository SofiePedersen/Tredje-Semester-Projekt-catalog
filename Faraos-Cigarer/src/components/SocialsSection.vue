<script setup></script>

<template>
  <div class="socials-section">
    <div class="socials-section__facebook">
      <p>FACEBOOK</p>
    </div>
    <div class="socials-section__instagram">
      <p>INSTAGRAM</p>
    </div>
    <div class="socials-section__tiktok">
      <p>TIKTOK</p>
    </div>
    <div class="socials-section__twitter">
      <p>TWITTER</p>
    </div>
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
}

.socials-section__instagram {
  width: 100%;
  height: 5rem;
  background-color: $color-pharaos-gold;
  color: $color-newspaper-white;
  -webkit-text-stroke: 0.1rem $color-anubis-black;
  font-family: $font-boogaloo;
  font-size: 2.44rem;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
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
}

.socials-section__twitter {
  width: 100%;
  height: 5rem;
  background-color: $color-pharaos-gold;
  color: $color-newspaper-white;
  -webkit-text-stroke: 0.1rem $color-anubis-black;
  font-family: $font-boogaloo;
  font-size: 2.44rem;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
