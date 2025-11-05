<script setup></script>

<template>
  <header>
    <div class="header">
    <h1 class="header__logo">Faraos Cigarer</h1>
    <input class="header__search" type="text" placeholder="søg" />
    </div>
  </header>
</template>

<style scoped>
.header{
    display: flex;
    flex-wrap: wrap;
}

.header__logo {
    display: flex;
    justify-content: center;
    align-items: center;
    font-family: 'Boogaloo';
}

.search__header {
    display: flex;
    justify-content: center;
}
</style>