<script setup>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { faMagnifyingGlass } from "@fortawesome/free-solid-svg-icons";
</script>

<template>
  <header>
    <div class="header">
        <img class="header__logo" src="../assets/image/faraos-logo.webp" alt="Faraos Cigarer Logo" />
      <div class="header__controls">
        <p class="header__icon">test</p>
        <input class="header__input" type="text" placeholder="søg" />
        <button><FontAwesomeIcon :icon="faMagnifyingGlass"/></button>
        <p class="header__icon">test</p>
      </div>
    </div>
  </header>
</template>

<style scoped>
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