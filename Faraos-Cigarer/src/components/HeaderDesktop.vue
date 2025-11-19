<script setup>
import FaraosLogo from "../assets/image/faraos-cigarer-logo-svg.svg";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { faMagnifyingGlass } from "@fortawesome/free-solid-svg-icons";
import { faCartShopping } from "@fortawesome/free-solid-svg-icons";
import { RouterLink } from "vue-router";
import MegamenuComp from "./MegamenuComp.vue";
</script>

<template>
  <header>
    <div class="header-logo-mini-wrapper">
      <div class="header-logo">
        <RouterLink to="/#">
          <img
            :src="FaraosLogo"
            alt="Logo for faraos"
            aria-label="Billed af faraos logo"
        /></RouterLink>
      </div>
      <div class="header-mini-navigation">
        <ul>
          <li>
            <RouterLink to="/#" class="mini-nav__link">SOCIALS</RouterLink>
          </li>
          <li>
            <RouterLink to="/Butikker" class="mini-nav__link"
              >BUTIKKER</RouterLink
            >
          </li>
          <li>
            <RouterLink to="/Butikker" class="mini-nav__link"
              >ÅBNINGSTIDER</RouterLink
            >
          </li>
          <li>
            <RouterLink to="/#" class="mini-nav__link">KALENDER</RouterLink>
          </li>
          <li>
            <RouterLink to="/#" class="mini-nav__link">KUNDESERVICE</RouterLink>
          </li>
          <li>
            <RouterLink to="/#" class="mini-nav__link"
              >MIN ØNSKELISTE</RouterLink
            >
          </li>
          <li>
            <RouterLink to="/#" class="mini-nav__link">LOGIN</RouterLink>
          </li>
        </ul>
      </div>
    </div>
    <div class="header-buttons-search-wrapper">
      <div class="header-button_wrapper">
        <ul>
          <MegamenuComp />
          <li>
            <RouterLink to="/#" class="button">KLUB FARAO</RouterLink>
          </li>
          <li>
            <RouterLink to="/#" class="button">NYHEDER</RouterLink>
          </li>
          <li>
            <RouterLink to="/#" class="button">TILBUD</RouterLink>
          </li>
        </ul>
      </div>
      <div class="search-basket">
        <form class="header-searchform">
          <input
            class="header__input"
            type="text"
            placeholder=""
            aria-label="søgefelt"
          />
          <button class="header__icon__search">
            <FontAwesomeIcon :icon="faMagnifyingGlass" aria-label="søgikon" />
          </button>
        </form>

        <div class="header__icon">
          <button class="header__icon__basket">
            <FontAwesomeIcon :icon="faCartShopping" aria-label="indkøbskurv" />
          </button>
        </div>
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>
@import "../assets/main.scss";

header {
  width: 100%;
  box-shadow: 0rem 0.4rem rgba(0, 0, 0, 0.25);
  display: none;
  margin-bottom: 1rem;
}

.header-logo-mini-wrapper {
  display: flex;
  justify-content: space-between;
  margin-left: 2rem;
  margin-right: 2rem;
}

.header-logo-mini-wrapper ul {
  display: flex;
  padding-top: 1rem;
  gap: 0.8rem;

  li {
    list-style-type: none;

    .mini-nav__link {
      text-decoration: none;
      font-family: $font-play;
      color: $color-anubis-black;
      font-size: 0.7rem;
      white-space: nowrap;
    }
  }
}

.header-logo-mini-wrapper img {
  width: 100%;
  min-width: 15rem;
  padding: 2rem 0rem;
}

.header-buttons-search-wrapper {
  display: flex;
  justify-content: space-between;
  margin-left: 2rem;
  margin-right: 2rem;
}

.header-button_wrapper {
  ul {
    display: flex;
    gap: 1rem;
    margin-bottom: 1rem;

    li {
      padding: 1rem;
      min-width: 4rem;
      height: 1.1rem;
      list-style-type: none;
      font-family: $font-boogaloo;
      background-color: $color-anubis-black;
      text-align: center;
      box-shadow: 0.3rem 0.3rem rgba(0, 0, 0, 0.25);
      white-space: nowrap;
      cursor: pointer;

      .button {
        text-decoration: none;
        color: $color-newspaper-white;
      }
    }
  }
}

.search-basket {
  display: flex;
  // justify-content:
  gap: 1rem;
}

.header-searchform {
  background: grey;
  width: 85%;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 3.1rem;
  box-shadow: 0.4rem 0.4rem rgba(0, 0, 0, 0.25);
}

.header__input {
  flex: 1;
  height: 100%;
  width: 60%;
  font-size: 1.5rem;
  border: 2px solid $color-anubis-black;
  background: white;
  color: $color-anubis-black;
  padding-left: 0.5rem;
  padding-right: 3rem;
}

.header__icon__search {
  position: absolute;
  top: 50%;
  right: 1rem;
  transform: translateY(-50%);
  background: none;
  border: none;
  color: $color-anubis-black;
  font-size: 1.5rem;
  cursor: pointer;
}

.header__icon {
  box-shadow: 0.3rem 0.3rem rgba(0, 0, 0, 0.25);
  margin-top: -0.15rem;
  height: 3.1rem;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 3.1rem;
  background-color: $color-anubis-black;
  border: 2px solid $color-anubis-black;
}

.header__icon__basket {
  border: none;
  background-color: $color-anubis-black;
  color: $color-newspaper-white;
  font-size: 1.6rem;
  cursor: pointer;
}

@media (min-width: 800px) {
  header {
    display: block;
  }
}
</style>
