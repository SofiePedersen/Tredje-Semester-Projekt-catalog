<script setup>
import FaraosLogo from "../assets/image/faraos-cigarer-logo-svg.svg";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { faMagnifyingGlass } from "@fortawesome/free-solid-svg-icons";
import { faCartShopping } from "@fortawesome/free-solid-svg-icons";
import { RouterLink } from "vue-router";
</script>

<template>
  <header>
    <div class="header-logo-mini-wrapper">
      <div class="header-logo">
        <img
          :src="FaraosLogo"
          alt="Logo for faraos"
          aria-label="Billed af faraos logo"
        />
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
          <li><RouterLink to="/#" class="mini-nav__link">LOGIN</RouterLink></li>
        </ul>
      </div>
    </div>
    <div class="header-buttons-search-wrapper">
      <div class="header-button_wrapper">
        <ul>
          <li><RouterLink to="/#" class="button">KATEGORIER</RouterLink></li>
          <li><RouterLink to="/#" class="button">KLUB FARAO</RouterLink></li>
          <li><RouterLink to="/#" class="button">NYHEDER</RouterLink></li>
          <li><RouterLink to="/#" class="button">TILBUD</RouterLink></li>
        </ul>
      </div>
      <div class="search-basket">
        <form id="searchform">
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
  background-color: aqua;
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
  gap: 1rem;

  li {
    list-style-type: none;

    .mini-nav__link {
      text-decoration: none;
      font-family: $font-play;
      color: $color-anubis-black;
      font-size: 0.8rem;
    }
  }
}

.header-logo-mini-wrapper img {
  width: 100%;
  padding: 2rem 0rem;
}

.header-buttons-search-wrapper {
  display: flex;
  justify-content: space-between;
}

.header-button_wrapper {
  ul {
    display: flex;
    gap: 1rem;
    margin-left: 2rem;
    margin-bottom: 1rem;

    li {
      padding: 1rem;
      min-width: 4rem;
      list-style-type: none;
      font-family: $font-boogaloo;
      background-color: $color-anubis-black;
      text-align: center;
      box-shadow: 0.4rem 0.4rem rgba(0, 0, 0, 0.25);

      .button {
        text-decoration: none;
        color: $color-newspaper-white;
      }
    }
  }
}

#searchform {
  background: grey;
  border-radius: 25px;
  width: 60%;
  position: relative;
  display: flex;
  justify-content: center;
}

@media (min-width: 1200px) {
  .header-logo-mini-wrapper {
    margin-left: 15rem;
    margin-right: 15rem;
  }

  .header-buttons-search-wrapper {
    margin-left: 15rem;
    margin-right: 15rem;
  }
  .header-button_wrapper {
    ul {
      margin-left: 0;
    }
  }
}
</style>
