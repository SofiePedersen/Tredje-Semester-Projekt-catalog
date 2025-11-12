<script setup>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { faAngleDown } from '@fortawesome/free-solid-svg-icons';
import { ref } from 'vue';
import { RouterLink } from 'vue-router';


const storeMapSections = ref([
  {
    id: 'jylland',
    title: 'JYLLAND',
    items: [
      { id: 'j1', title: 'Find alle de lokale butikker på Jylland!', url: '#' },
      { id: 'j2', title: 'Aarhus games', url: '#' },
      { id: 'j3', title: 'Aarhus comics', url: '#' },
    ],
  },
  {
    id: 'fyn',
    title: 'FYN',
    items: [
      { id: 'f1', title: 'Find alle de lokale butikker på Fyn!', url: '#' },
      { id: 'f2', title: 'Odense', url: '/information' },
    ],
  },
  {
    id: 'sjaelland',
    title: 'SJÆLLAND',
    items: [
      { id: 's1', title: 'Find alle de lokale butikker på Sjælland!', url: '#' },
      { id: 's2', title: 'København comics & potter', url: '#' },
      { id: 's3', title: 'København bræt- & rollespil', url: '#' },
      { id: 's4', title: 'København figurspil', url: '#' },
    ],
  },
]);

const openSection = ref(null);

function toggleSection(id) {
  openSection.value = openSection.value === id ? null : id;
}
</script>


<template>
  <div class="stores-wrapper">
    <nav class="breadcrumbs" aria-label="Navigations brødkrummer">
      <RouterLink class="breadcrumbs__text" to="/" aria-label="Navigation til forsiden">Forside</RouterLink>
      <p class="breadcrumbs__text">></p>
      <RouterLink class="breadcrumbs__text" to="/Butikker" aria-label="Navigation til oversigten over butikker">Butikker
      </RouterLink>
      <p class="breadcrumbs__text">></p>
      <RouterLink class="breadcrumbs__text" to="/Information" aria-label="Navigation til Odense butik">Odense
      </RouterLink>
    </nav>

    <div class="map-container" aria-label="Google maps over butikkens lokation">
        <iframe
          src="https://www.google.com/maps/embed?pb=!1m16!1m12!1m3!1d577050.2589892185!2d10.37101225287178!3d55.60022845645195!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!2m1!1sFaraos%20Cigarer!5e0!3m2!1sda!2sdk!4v1762941964703!5m2!1sda!2sdk"
          width="100%" height="500rem" style="border:0;" allowfullscreen="" loading="lazy"
          referrerpolicy="no-referrer-when-downgrade"></iframe>
    </div>

    <h2>HVOR VIL DU HEN?</h2>

    <div v-for="section in storeMapSections" :key="section.id" class="butikker__sektion" @click="toggleMenu"
      aria-label="landsdele sektioner">
      <button class="butikker__sektion--knap" @click="toggleSection(section.id)" aria-label="åben/luk felt">
        {{ section.title }}
        <FontAwesomeIcon :icon="faAngleDown" :class="{ 'rotate-180': openSection === section.id }" class="butikker__ikon"
          aria-label="åben/luk pil" />
      </button>

      <transition name="slide-fade">
        <div class="listitem__controls">
          <ul v-if="openSection === section.id" class="butikker__sektion__boks" aria-label="informations boks">
            <li v-for="item in section.items" :key="item.id" class="butikker__sektion__listitem">
              <RouterLink :to="item.url" class="butikker__links">{{ item.title }}</RouterLink>
            </li>
          </ul>
        </div>
      </transition>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/main.scss";

.stores-wrapper {
  padding: 2rem;
  padding-top: 0.5rem;
}

.breadcrumbs {
  display: flex;
  justify-content: flex-start;
  padding:0rem 0rem 2rem 0rem;

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
  color: $color-tactical-blue;
}

.butikker__sektion {
  display: flex;
  flex-direction: column;
  margin-bottom: 1.5rem;
  justify-content: center;
  align-items: center;
  color: $color-pharaos-gold;
  background-color: $color-anubis-black;
}

.butikker__sektion:last-of-type {
  margin-bottom: 0;
}

.butikker__ikon {
  transition: transform 0.3s ease;
  transform: rotate(0deg);
  transform-origin: center;
  backface-visibility: hidden;
}

.butikker__ikon.rotate-180 {
  transform: rotate(180deg);
}


.butikker__sektion--knap {
  background: none;
  border: none;
  color: $color-pharaos-gold;
  font-size: 1.5rem;
  padding: 1rem;
  width: 100%;
  text-align: center;
  display: flex;
  justify-content: center;
  justify-content: space-between;
  align-items: center;
  font-family: $font-boogaloo;
  cursor: pointer;
}

.listitem__controls {
  width: 100%;
  background-color: $color-pharaos-gold;
}

.butikker__sektion__boks {
  width: 100%;
  padding: 1.5rem;
  color: $color-anubis-black;
}

.butikker__links {
  text-decoration: none;
  font-family: $font-play;
  color: $color-anubis-black;
}

.butikker__sektion__listitem {
  margin-left: 1rem;
}

.butikker__sektion__listitem:first-of-type {
  list-style-type: none;
  margin: 0;
  margin-bottom: 1rem;
}
</style>
