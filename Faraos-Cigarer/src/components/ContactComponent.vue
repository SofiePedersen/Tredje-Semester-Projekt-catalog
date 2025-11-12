<script setup>
import FaraosCigarerRoar from "@/assets/image/faraos-cigarer-roar.webp";
</script>

<template>
  <div class="opening-hours" aria-label="Åbningstider for Faraos Cigarer">
    <h3 class="opening-hours__titel">ÅBNINGSTIDER</h3>
    <div class="opening-hours__text--breaks" aria-label="Hverdage">
      <p>Hverdage:</p>
      <p>Mandag - Fredag: 10:00 - 18:00</p>
    </div>
    <div class="opening-hours__text--breaks" aria-label="Weekendtider">
      <p>Weekendtider:</p>
      <p>Lørdag - 10:00 - 17:00</p>
      <p>Søndag - 11:00 - 16:00</p>
    </div>
    <div class="opening-hours__text--breaks" aria-label="Særlige lukkedage">
      <p>
        *Faraos Cigarer holder dog søndagslukket, når søndag falder på en
        helligdag.
      </p>
    </div>
  </div>

  <div class="contact" aria-label="Kontaktinformation for Faraos Cigarer">
    <h3 class="contact__titel">KONTAKT</h3>
    <div class="contact__text--breaks" aria-label="Adresse">
      <p>Faraos Cigarer - Odense</p>
      <p>Klostervej 3,</p>
      <p>5000 Odense C</p>
    </div>
    <div class="contact__text--breaks" aria-label="Telefonnummer">
      <p>Telefon:</p>
      <p>+45 65 91 97 01</p>
    </div>
    <div class="contact__text--breaks" aria-label="E-mail adresse">
      <p>E-mail:</p>
      <p>Odense@faraos.dk</p>
    </div>
  </div>

  <div class="closing-days" aria-label="Lukkedage for Faraos Cigarer">
    <p>Faraos Cigarer holder desuden lukket de følgende dage:</p>
    <ul>
      <li>Nytårsdag</li>
      <li>Skærtorsdag</li>
      <li>Langfredag</li>
      <li>Kristi Himmelfartsdag</li>
      <li>Grundlovsdag</li>
      <li>1. og 2. pinsedag</li>
      <li>Juleaftensdag</li>
      <li>1. og 2. juledag</li>
      <li>Nytårsaftensdag (Lukker fra kl. 15)</li>
    </ul>
    <img
      :src="FaraosCigarerRoar"
      alt="Bil som laver en lyd"
      aria-label="Billede af en bil med lyd-effekt"
    />
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/main.scss";

.opening-hours {
  margin: 2rem;
  padding: 2rem;
  color: $color-newspaper-white;
  background-color: $color-anubis-black;
}

.opening-hours h3 {
  color: $color-pharaos-gold;
  font-family: $font-boogaloo;
  font-size: 2.44rem;
  font-weight: 100;
}

.opening-hours p {
  font-family: $font-play;
}

.opening-hours__text--breaks {
  padding-top: 1rem;
}

.contact {
  margin: 2rem;
  padding: 2rem;
  background-color: $color-pharaos-gold;
}

.contact p {
  font-family: $font-play;
}

.contact__text--breaks {
  padding-top: 1rem;
}

.contact h3 {
  color: $color-newspaper-white;
  font-family: $font-boogaloo;
  font-size: 2.44rem;
  -webkit-text-stroke: 0.1rem $color-anubis-black;
  font-weight: 100;
}

.closing-days {
  margin: 2rem;
  padding: 2rem;
  font-family: $font-play;
  color: $color-newspaper-white;
  background-color: $color-anubis-black;
}
.closing-days ul {
  padding-top: 1rem;
  padding-left: 1.5rem;
}
.closing-days li {
  padding-top: 1rem;
}

.closing-days img {
  display: block;
  margin: 1rem auto;
  max-width: 100%;
  height: auto;
  object-fit: cover;
}
</style>
