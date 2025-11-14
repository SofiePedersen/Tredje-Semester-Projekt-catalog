<script setup>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { faAngleDown } from '@fortawesome/free-solid-svg-icons';
import { faMagnifyingGlass } from "@fortawesome/free-solid-svg-icons";
import { faCartShopping } from "@fortawesome/free-solid-svg-icons";
import { ref } from "vue";
import { useRouter } from "vue-router";
import { onMounted } from "vue";

const isMenuActive = ref(false);
const togglemenu = () => {
  isMenuActive.value = !isMenuActive.value; 
};

const router = useRouter();

onMounted(() => {
  router.afterEach(() => {
    isMenuActive.value = false;
  });
});

const burgerMenuSelection = ref([
  {
    id: 'Kategorier',
    title: 'KATEGORIER',
    items: [
      { id: 'K1', title: 'Bøger og tegneserier', url: '#' },
      { id: 'K2', title: 'Aarhus games', url: '#' },
      { id: 'K3', title: 'Aarhus comics', url: '#' },
    ],
  },
  {
    id: 'KlubFaraos',
    title: 'KLUB FARAOS',
    items: [
      { id: 'f1', title: 'Find alle de lokale butikker på Fyn!', url: '#' },
      { id: 'f2', title: 'Odense', url: '/information' },
    ],
  },
  {
    id: 'Nyheder',
    title: 'NYHEDER',
    items: [
      { id: 's1', title: 'Find alle de lokale butikker på Sjælland!', url: '#' },
      { id: 's2', title: 'København comics & potter', url: '#' },
      { id: 's3', title: 'København bræt- & rollespil', url: '#' },
      { id: 's4', title: 'København figurspil', url: '#' },
    ],
  },
  {
    id: 'Tilbud',
    title: 'TILBUD',
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
  <header>

    <div class="header">      
        <RouterLink to="/">
          <img alt="faraos logo" class="header__logo" src="../assets/image/faraos-cigarer-logo-svg.svg">
        </RouterLink>

      <div class="header__controls">
        <nav id="hammenu__nav" class="off-screen-menu" :class="{ active: isMenuActive }">
          <div class="burgermenu__wrapper">
            <img alt="faraos logo" class="header__logo__burgermenu" src="../assets/image/faraos-cigarer-logo-svg.svg">
            <div class="burgermenu__buttons">
              <div class="ham-menu__burgermenu" :class="{ active: isMenuActive }" @click="togglemenu" aria-label="burgermenu knap">
                <span></span>
                <span></span>
                <span></span>
              </div>
              <form id="searchform">
                <input class="header__input__burgermenu" type="text" placeholder="" aria-label="søgefelt"/>
                <button class="header__icon__search__burgermenu"><FontAwesomeIcon :icon="faMagnifyingGlass" aria-label="søgikon"/></button>
              </form>
              <div class="header__icon__burgermenu">
                <button class="header__icon__basket__burgermenu"><FontAwesomeIcon :icon="faCartShopping" aria-label="indkøbskurv" /></button>
              </div>
            </div>
        </div>

          <div v-for="section in burgerMenuSelection" :key="section.id" class="burgermenu__sektion" @click="toggleMenu"
             aria-label="burgermenu punkter">
              <button class="burgermenu__section--button" @click="toggleSection(section.id)" aria-label="åben/luk felt">
                 {{ section.title }}
                <FontAwesomeIcon :icon="faAngleDown" :class="{ 'rotate-180': openSection === section.id }" class="burgermenu__ikon"
                aria-label="åben/luk pil" />
              </button>

      <transition name="slide-fade">
        <div class="listitem__controls">
          <ul v-if="openSection === section.id" class="burgermenu__section__boks" aria-label="informations boks">
            <li v-for="item in section.items" :key="item.id" class="burgermenu__section__listitem">
              <RouterLink :to="item.url" class="burgermenu__links">{{ item.title }}</RouterLink>
            </li>
          </ul>
        </div>
      </transition>
    </div>
        </nav>

        <div class="ham-menu" :class="{ active: isMenuActive }" @click="togglemenu" aria-label="burgermenu knap">
          <span></span>
          <span></span>
          <span></span>
        </div>

        <form id="searchform">
        <input class="header__input" type="text" placeholder="" aria-label="søgefelt"/>
        <button class="header__icon__search"><FontAwesomeIcon :icon="faMagnifyingGlass" aria-label="søgikon"/></button>
        </form>

        <div class="header__icon">
        <button class="header__icon__basket"><FontAwesomeIcon :icon="faCartShopping" aria-label="indkøbskurv" /></button>
        </div>
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>
@import '../assets/main.scss';

.off-screen-menu {
  background-color: $color-pharaos-gold;
  height: 100vh;
  width: 100%;
  max-width: 480px;
  position: fixed;
  top: 0;
  left: -500px;
  font-family: 'play';
  display: flex;
  flex-direction: column;
  transition: .3s ease;
  z-index: 1;
}

.burgermenu__wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 1rem;
    gap: 1rem;
}

#menu {
    list-style: none;
    font-family: "play";
}

.header__hammenu__list {
    margin: 25% 0;
}


.header__hammenu__searchtag:link, .header__hammenu__searchtag:visited, .header__hammenu__searchtag:hover, .header__hammenu__searchtag:active { 
    color: white; 
    text-decoration: none;
}

.off-screen-menu.active{
    left: 0;
}

.ham-menu {
    height: 50px;
    width: 50px;
    margin: auto;
    position: relative;
    background-color: black;
}

.ham-menu__burgermenu {
    height: 50px;
    width: 50px;
    margin: auto;
    position: relative;
    background-color: black;
}

.ham-menu__burgermenu span{
    height: 2px;
    width: 70%;
    background-color: white;
    border-radius: 25px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    transition: .3s ease;
    z-index: 2;
}

.ham-menu span{
    height: 2px;
    width: 70%;
    background-color: white;
    border-radius: 25px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}

.ham-menu span:nth-child(1) {
    top: 25%;
}

.ham-menu span:nth-child(3) {
    top: 75%;
}

.ham-menu__burgermenu.active span:nth-child(1) {
    top: 50%;
    transform: translate(-50%, -50%) rotate(45deg);
}

.ham-menu__burgermenu.active span:nth-child(2) {
    opacity: 0;
}

.ham-menu__burgermenu.active span:nth-child(3) {
    top: 50%;
    transform: translate(-50%, -50%) rotate(-45deg);
}

.burgermenu__section {
  display: flex;
  flex-direction: column;
  margin-bottom: 1.5rem;
  justify-content: center;
  align-items: center;
  color: $color-pharaos-gold;
  background-color: $color-anubis-black;
}

.burgermenu__section:last-of-type {
  margin-bottom: 0;
}

.burgermenu__ikon {
  transition: transform 0.3s ease;
  transform: rotate(0deg);
  transform-origin: center;
  backface-visibility: hidden;
}

.burgermenu__ikon.rotate-180 {
  transform: rotate(180deg);
}
.burgermenu__section--button {
  background: none;
  border: none;
  color: white;
  font-size: 1.5rem;
  padding: 1rem;
  width: 100%;
  text-align: center;
  display: flex;
  justify-content: center;
  justify-content: space-between;
  align-items: center;
  font-family: $font-boogaloo;
  background-color: $color-anubis-black;
  cursor: pointer;
}

.listitem__controls {
  width: 100%;
  background-color: $color-anubis-black;
}

.burgermenu__section__boks {
  width: 100%;
  padding: 1.5rem;
  color: $color-anubis-black;
}

.burgermenu__links {
  text-decoration: none;
  font-family: $font-play;
  color: white;
}

.burgermenu__section__listitem {
  margin-left: 1rem;
  list-style-type: none;
}

.burgermenu__section__listitem:first-of-type {
  list-style-type: none;
  margin: 0;
  margin-bottom: 1rem;
}

.header {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.header__controls {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  gap: 10px; 
  margin-top: 10px;
  margin-bottom: 5%;
}

.header__logo {
  display: flex;
  justify-content: center;
  width:  290px;
  height: auto;
  margin: auto;
  padding-bottom: 1rem;
  padding-top: 1rem;
}

.header__logo__burgermenu {
  display: flex;
  justify-content: center;
  width:  290px;
  height: auto;
}

#searchform {
  background: grey;
  border-radius: 25px;
  width: 60%;
  position: relative;
  display: flex;
  justify-content: center;
}

.header__input {
  width: 100%;
  height: 100%;
  display: block;
  border-width: 3px;
  font-size: 24px;
  padding: 8px 40px 8px 20px;
  border: 2px solid $color-anubis-black;
}

.header__input__burgermenu {
  width: 100%;
  display: block;
  border-width: 3px;
  font-size: 24px;
  padding: 8px 40px 8px 20px;
  border: 2px solid $color-anubis-black;
}

.header__icon__search {
  position: absolute;
  top: 50%;
  right: 10px;
  transform: translateY(-50%);
  background: none;
  border: none;
  color: black;
  font-size: 20px;
  cursor: pointer;
}

.header__icon__search__burgermenu {
  position: absolute;
  top: 50%;
  right: 10px;
  transform: translateY(-50%);
  background: none;
  border: none;
  color: black;
  font-size: 20px;
  cursor: pointer;
}

.header__icon {
  white-space: nowrap;
  background-color: #000000;
  margin: auto;
}

.header__icon__burgermenu {
  white-space: nowrap;
}

.header__icon__basket {
  height: 50px;
  width: 50px;
  padding-top: 5px;
  margin-left: auto;
  margin-right: auto;
  border: none;
  position: relative;
  background-color: black;
  color: white;
  font-size: 28px;
}

.header__icon__basket__burgermenu {
  height: 50px;
  width: 50px;
  padding-top: 5px;
  margin-left: auto;
  margin-right: auto;
  border: none;
  position: relative;
  background-color: black;
  color: white;
  font-size: 28px;
}

.burgermenu__buttons {
  display: flex;
  justify-content: flex-end;
}

.burgermenu__buttons .header__icon__basket__burgermenu {
  margin-left: 2rem;
}
</style>