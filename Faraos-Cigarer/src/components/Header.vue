<script setup>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { faAngleDown } from '@fortawesome/free-solid-svg-icons';
import { faMagnifyingGlass } from "@fortawesome/free-solid-svg-icons";
import { faCartShopping } from "@fortawesome/free-solid-svg-icons";
import { ref } from "vue";
import { useRouter } from "vue-router";
import { onMounted } from "vue";
import  HeaderData  from "../HeaderData.json";
import HeaderDataTwo from "../HeaderDataTwo.json";

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



class MenuCategory {
  constructor(id, title, items = []) {
    this.id = id;
    this.title = title;
    this.items = items;
  }

  addItem(item) {
    this.items.push(item);
  }
}



const burgerMenuSelection = HeaderData.map(obj =>
  new MenuCategory(obj.id, obj.title, obj.items))

const burgerMenuDataTwo = HeaderDataTwo.map(obj =>
  new MenuCategory(obj.id, obj.title, obj.items))


const categoryId = ref(0);


const openSection = ref(null);

const openCategory = ref(null);

function toggleSection(id) {
  openSection.value = openSection.value === id ? null : id;
}

function toggleCategory(id) {
  openCategory.value = openCategory.value === id ? null : id;
}

console.log(burgerMenuSelection)
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

        <div class="burgermenu__sektion" @click="toggleMenu" aria-label="burgermenu punkter">
          <button class="burgermenu__section--button" @click="toggleSection(categoryId)" aria-label="åben/luk felt">
                {{ "Kategorier" }}
              <FontAwesomeIcon :icon="faAngleDown" :class="{ 'rotate-180': openSection === categoryId }" class="burgermenu__ikon"
              aria-label="åben/luk pil" />
            </button>
          <ul v-if="openSection === categoryId" id="menu" class="header__hammenu__list" aria-label="burgermenu liste"> 
            <li v-for="categoryItem in burgerMenuSelection" :key="categoryItem.id" class="burgermenu__sektion" @click="toggleMenu" aria-label="burgermenu punkter">
            <button class="burgermenu__section__inner--button" @click="toggleCategory(categoryItem.id)" aria-label="åben/luk felt">
                {{ categoryItem.title }}
              <FontAwesomeIcon :icon="faAngleDown" :class="{ 'rotate-180': openCategory === categoryItem.id }" class="burgermenu__ikon"
              aria-label="åben/luk pil" />
            </button>
              <div class="listitem__controls">
                <ul v-if="openCategory === categoryItem.id" class="burgermenu__section__boks" aria-label="informations boks">
                  <li v-for="item in categoryItem.items" :key="item.id" class="burgermenu__section__listitem">
                    <RouterLink :to="item.url" class="burgermenu__links">{{ item.title }}</RouterLink>
                    <ul v-if="openCategory === categoryItem.id"> 
                      <li v-for="innersection in item.items" :key="innersection.id" class="burgermenu__section__listitem__inner">
                        <RouterLink :to="innersection.url" class="burgermenu__links__inner">{{ innersection.title }}</RouterLink>
                      </li>
                    </ul>
                  </li>
                </ul>
              </div>
            </li>
          </ul>
        </div>
        
        <div v-for="section in burgerMenuDataTwo" :key="section.id" class="burgermenu__sektion" @click="toggleMenu" aria-label="burgermenu punkter">
          <button class="burgermenu__section--button" @click="toggleSection(section.id)" aria-label="åben/luk felt">
                {{ section.title }}
              <FontAwesomeIcon :icon="faAngleDown" :class="{ 'rotate-180': openSection === section.id }" class="burgermenu__ikon"
              aria-label="åben/luk pil" />
            </button>
          <ul v-if="openSection === section.id" id="menu" class="header__hammenu__list" aria-label="burgermenu liste"> 
            <li v-for="categoryItem in section.items" :key="categoryItem.id" class="burgermenu__sektion" @click="toggleMenu" aria-label="burgermenu punkter">
            <p class="burgermenu__section__inner--button" @click="toggleCategory(categoryItem.id)" aria-label="åben/luk felt">
                {{ categoryItem.title }}
            </p>
            </li>
          </ul>
        </div>

          <h2 class="burgermenu__service__overskrift">HAR DU BRUG FOR HJÆLP?</h2>


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

.off-screen-menu { 
    background-image: url("../assets/image/community_1.webp");
    background-repeat: no-repeat;
    background-size: 65%;
    background-position: 0 36rem;
    background-image: reverse;
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
    margin-right: 2rem;
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

.burgermenu__sektion__service{
  display: flex;
  justify-content: center;
}

.burgermenu__section__service--button {
  background: none;
  color: white;
  font-size: 1.5rem;
  border: none;
  padding: 1rem;
  width: 70%;
  text-align: center;
  margin: 2% 0;
  display: flex;
  justify-content: space-between;
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
  font-size: 1.2rem;
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
  padding-bottom: 1rem;
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

.burgermenu__service__overskrift {
  color: white;
}

.burgermenu__section__listitem__inner {
  margin-bottom: 2rem;
}

.burgermenu__links__inner {
  text-decoration: none;
  font-family: $font-play;
  font-size: 1rem;
  margin-left: 2rem;
  color: white;
}



.burgermenu__section__inner--button {
  background: none;
  border: none;
  color: white;
  font-size: 1rem;
  padding: 1rem;
  width: 100%;
  text-align: center;
  display: flex;
  justify-content: center;
  justify-content: space-between;
  align-items: center;
  font-family: $font-play;
  background-color: $color-anubis-black;
  cursor: pointer;
}


@media (min-width: 800px) {
  header {
    display: none;
  }
}
</style>