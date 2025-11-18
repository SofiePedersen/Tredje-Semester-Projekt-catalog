<script>
import { RouterLink } from "vue-router";
</script>

<template>
  <div class="stores-wrapper">
    <div class="stores-titles">
      <div class="stores-titles-jylland">Jylland</div>
      <div class="stores-titles-fyn">Fyn</div>
      <div class="stores-titles-sjælland">Sjælland</div>
    </div>

    <div class="stores-cities">
      <div class="stores-cities-jylland">
        <p>Find alle de lokale butikker på Jylland her:</p>
        <ul>
          <li>Aarhus Games</li>
          <li>Aarhus Comics</li>
        </ul>
      </div>
      <div class="stores-citites-fyn">
        <p>Find alle de lokale butikker på fyn her:</p>
        <ul>
          <li>
            <RouterLink to="/Information">Odense</RouterLink>
          </li>
        </ul>
      </div>
      <div class="stores-citites-sjælland">
        <p>Find alle de lokale butikker på Sjælland her:</p>
        <ul>
          <li>København Comics & Potter</li>
          <li>København Bræt- & Rollespil</li>
          <li>København Figurspil</li>
          <li>København Kortspil</li>
          <li>København Manga</li>
          <li>København Udklædning & Liverollespil</li>
          <li>København Merchandise</li>
          <li>Lyngby Games</li>
          <li>Lyngby Comics</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/main.scss";

.stores-wrapper {
  display: none;
}

.stores-titles {
  display: flex;
  gap: 1rem;
  padding-left: 2rem;
  padding-right: 2rem;

  > div {
    background: $color-anubis-black;
    font-family: $font-boogaloo;
    color: $color-pharaos-gold;
    padding: 1.5rem;
    font-size: 2.44rem;
    flex: 1;
    text-align: center;
  }
}

.stores-cities {
  display: flex;
  gap: 1rem;
  padding-top: 1rem;
  padding-left: 2rem;
  padding-right: 2rem;
  padding-bottom: 2rem;

  > div {
    font-family: $font-play;
    background: $color-pharaos-gold;
    color: $color-anubis-black;
    padding: 2rem;
    padding-top: 1.5rem;
    flex: 1;

    li {
      padding-top: 1rem;
      margin-left: 1rem;
      cursor: pointer;

      a {
        color: inherit;
        text-decoration: none;
      }
    }
  }
}

@media (min-width: 601px) {
  .stores-wrapper {
    display: block;
  }
}

@media (min-width: 1200px) {
  .stores-titles {
    padding-left: 15rem;
    padding-right: 15rem;
  }

  .stores-cities {
    padding-left: 15rem;
    padding-right: 15rem;
  }
}
</style>
