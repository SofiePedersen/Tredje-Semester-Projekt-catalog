<script setup></script>

<template>
  <nav class="breadcrumbs" aria-label="Navigations brødkrummer">
    <RouterLink
      class="breadcrumbs__text"
      to="/"
      aria-label="Navigation til forsiden"
      >Forside</RouterLink
    >
    <p class="breadcrumbs__text">></p>
    <RouterLink
      class="breadcrumbs__text"
      to="/Butikker"
      aria-label="Navigation til oversigten over butikker"
      >Butikker</RouterLink
    >
    <p class="breadcrumbs__text">></p>
    <RouterLink
      class="breadcrumbs__text"
      to="/Information"
      aria-label="Navigation til Odense butik"
      >Odense</RouterLink
    >
  </nav>

  <div class="map-container" aria-label="Google maps over butikkens lokation">
    <iframe
      src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2687.642260674874!2d10.38035027706906!3d55.39705671933529!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x464cdff9c0d87ce7%3A0x1ec4b00069831865!2sFaraos%20Cigarer!5e1!3m2!1sen!2sdk!4v1762941660760!5m2!1sen!2sdk"
      width="100%"
      height="500rem"
      style="border: 0"
      allowfullscreen=""
      loading="lazy"
      referrerpolicy="no-referrer-when-downgrade"
    ></iframe>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/main.scss";

.breadcrumbs {
  display: flex;
  justify-content: flex-start;
  margin-left: 2rem;
  margin-top: 1rem;

  p {
    margin-left: 0.5rem;
    margin-right: 0.5rem;
  }
}

.breadcrumbs__text {
  font-size: 1rem;
  color: $color-anubis-black;
  text-decoration: none;
  font-family: $font-play;
}

.breadcrumbs__text:hover {
  color: #3396e6;
}

.map-container {
  padding: 2rem;
  padding-bottom: 0;
}

@media (min-width: 1200px) {
  .breadcrumbs {
    padding-left: 15rem;
    padding-right: 15rem;
  }

  .map-container {
    padding-left: 15rem;
    padding-right: 15rem;
  }
}
</style>
