<script setup>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { faMagnifyingGlass } from "@fortawesome/free-solid-svg-icons";
import { ref } from "vue";

const isMenuActive = ref(false);
const togglemenu = () => {
  isMenuActive.value = !isMenuActive.value; 
};

const menuItems = [
  { name: "Hjem", link: "/" },
  { name: "Cigarer", link: "/cigarer" },
  { name: "Tilbehør", link: "/tilbehor" },
  { name: "Om Os", link: "/om-os" },
  { name: "Kontakt", link: "/kontakt" },
];

</script>

<template>
  <header>
    <div class="header">
        <img class="header__logo" src="../assets/image/faraos-logo.webp" alt="Faraos Cigarer Logo" />
      <div class="header__controls">
        <nav class="off-screen-menu" :class="{ active: isMenuActive }">
          <ul id="menu">
           <li v-for="item in menuItems" :key="item.name">
              <a :href="item.link">{{ item.name }}</a>
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
        <p class="header__icon">test</p>
      </div>
    </div>
  </header>
</template>

<style scoped>

.off-screen-menu {
  background-color: #fffcf3;
  height: 100vh;
  width: 100%;
  max-width: 450px;
  position: fixed;
  top: 0;
  right: -450px;
  color: #081907;
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

li {
    margin: 25% 0;
}

a:link, a:visited, a:hover, a:active { 
    color: #081907; 
    text-decoration: none;
}

.off-screen-menu.active{
    right: 0;
}

nav {
    padding: 1rem;
    display: flex;
    align-items: center;
    background-color: #fffcf3;
}

.ham-menu {
    height: 50px;
    width: 50px;
    margin-left: auto;
    position: relative;
}

.ham-menu span{
    height: 5px;
    width: 100%;
    background-color: #081907;
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
}
</style>