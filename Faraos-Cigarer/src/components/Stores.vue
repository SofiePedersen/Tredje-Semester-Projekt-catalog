<script setup>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { faAngleDown } from '@fortawesome/free-solid-svg-icons';
import { ref } from 'vue';
import { useRouter } from "vue-router";


const storeMapSections = ref([
  {
    id: 'jylland',
    title: 'JYLLAND',
    items: [
      { id: 'j1', title: 'AARHUS GAMES', url: '#' },
      { id: 'j2', title: 'AARHUS COMICS', url: '#' },
    ],
  },
  {
    id: 'fyn',
    title: 'FYN',
    items: [
      { id: 'f1', title: 'ODENSE', url: '#' },
    ],
  },
  {
    id: 'sjaelland',
    title: 'SJÆLLAND',
    items: [
      { id: 's1', title: 'KØBENHAVN COMICS & POTTER', url: '#' },
      { id: 's2', title: 'KØBENHAVN BRÆT- & ROLLESPIL', url: '#' },
      { id: 's3', title: 'KØBENHAVN FIGURSPIL', url: '#' },
    ],
  },
]);

const openSection = ref(null);

function toggleSection(id) {
  openSection.value = openSection.value === id ? null : id;
}
</script>


<template>
  <img class="butikker__kort" src="@/assets/image/Landekort.webp" alt="Landkort" />
  <h2>HVOR VIL DU HEN?</h2>

  <div v-for="section in storeMapSections" :key="section.id" class="butikker__sektion">
    <button class="butikker__sektion-knap" @click="toggleSection(section.id)">
      {{ section.title }}
      <FontAwesomeIcon :icon="faAngleDown" :class="{'rotate-180': openSection === section.id}" />
    </button>
    <transition name="slide-fade">
      <ul v-if="openSection === section.id" class="butikker__sektion__boks">
        <li v-for="item in section.items" :key="item.id" class="butikker__sektion__listitem">
          <RouterLink :to="item.url" class="butikker__links">{{ item.title }}</RouterLink>
        </li>
      </ul>
    </transition>
  </div>

 
</template>

<style lang="scss" scoped>
@import "../assets/main.scss";

.butikker__kort {
  width: 100%;
  height: auto;
}

.butikker__sektion {
  display: flex;
  flex-direction: column;
  margin-bottom: 1rem;
  justify-content: center;
  align-items: center;
  margin-left: 20%;
  margin-right: 20%;
  color: $color-pharaos-gold;
  background-color: $color-anubis-black;
}

.butikker__sektion__boks {
  list-style: none;
  padding: 0;
  margin: 0.5rem 0;
  width: 100%;
  color: $color-pharaos-gold;
  text-align: center;
  justify-content: center;
}

.butikker__links {
  justify-content: center;
  text-decoration: none;
  color: $color-pharaos-gold;
}

.butikker__sektion__listitem {
  margin: 3rem 0;
  justify-content: center;
}


.slide-fade-enter-active {
  transition: all 250ms ease;
}
.slide-fade-leave-active {
  transition: all 200ms ease;
}
.slide-fade-enter-from {
  opacity: 0;
  transform: translateY(-6px);
}
.slide-fade-enter-to {
  opacity: 1;
  transform: translateY(0);
}
.slide-fade-leave-from {
  opacity: 1;
  transform: translateY(0);
}
.slide-fade-leave-to {
  opacity: 0;
  transform: translateY(-6px);
}
</style>
