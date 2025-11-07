<script setup>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
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


// yo mr scrummy her, de her elementer skal lige opdateres når vi har sat routes op for lige nu kan de ikke load den nye side da det SKAL matche før det er aktivt, men det skulle virke
const menuItems = [
  { name: "Hjem", link: "/" },
  { name: "Butikker", link: "/Butikker" },
  { name: "Åbningstider", link: "/Information" },
];

</script>

<template>
  <header>
    <div class="header">
        <img class="header__logo" src="../assets/image/faraos-logo.webp" alt="Faraos Cigarer Logo" />
      <div class="header__controls">
        <nav id="hammenu__nav" class="off-screen-menu" :class="{ active: isMenuActive }">
          <ul id="menu">
           <li class="header__hammenu__list" v-for="item in menuItems" :key="item.name">
              <!--<a class="header__hammenu__a" :href="item.link">{{ item.name }}</a>-->
              <router-link class="header__hammenu__searchtag" :to="item.link">{{ item.name }}</router-link>
            </li>             
          </ul>
        </nav>
        <div class="ham-menu" :class="{ active: isMenuActive }" @click="togglemenu">
          <span></span>
          <span></span>
          <span></span>
        </div>
        <input class="header__input" type="text" placeholder="søg" />
        <button><FontAwesomeIcon :icon="faMagnifyingGlass"/></button>
        <div class="header__icon">
        <button class="header__icon__basket"><FontAwesomeIcon :icon="faCartShopping" /></button>
        </div>
      </div>
    </div>
  </header>
</template>

<style scoped>

.off-screen-menu {
  background-color: #000000;
  height: 100vh;
  width: 100%;
  max-width: 450px;
  position: fixed;
  top: 0;
  left: -500px;
  font-family: 'play';
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  font-size: 3rem;
  transition: .3s ease;
  z-index: 1;
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

#hammenu__nav {
    padding: 1rem;
    display: flex;
    align-items: center;
    background-color: #000000;
}

.ham-menu {
    height: 50px;
    width: 50px;
    margin-left: auto;
    position: relative;
    background-color: black;
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
    transition: .3s ease;
    z-index: 1;
}

.ham-menu span:nth-child(1) {
    top: 25%;
    z-index: 1;
}

.ham-menu span:nth-child(3) {
    top: 75%;
    z-index: 1;
}

.ham-menu.active span:nth-child(1) {
    top: 50%;
    transform: translate(-50%, -50%) rotate(45deg);
    z-index: 1;
}

.ham-menu.active span:nth-child(2) {
    opacity: 0;
    z-index: 1;
}

.ham-menu.active span:nth-child(3) {
    top: 50%;
    transform: translate(-50%, -50%) rotate(-45deg);
    z-index: 1;
}

.header {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
}

.header__controls {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  gap: 10px; 
  margin-top: 10px;
}

.header__logo {
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: 'Boogaloo';
  margin-bottom: 20px;
}

.header__input {
  width: 50%;
}

.header__icon {
  white-space: nowrap;
  background-color: #000000;
}

.header__icon__basket {
  height: 50px;
  width: 50px;
  margin-left: auto;
  margin-right: auto;
  border: none;
  position: relative;
  background-color: black;
  color: white;
  font-size: 28px;;
}
</style>