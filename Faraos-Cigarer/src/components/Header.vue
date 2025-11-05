<script setup></script>

<template>
  <header>
    <div class="header">
    <h1 class="header__logo">Faraos Cigarer</h1>
    <p class="header__icon">test</p>
    <input class="header__input" type="text" placeholder="søg" />
    </div>
  </header>
</template>

<style scoped>
.header{
    display: flex;
    flex-wrap: wrap;
    flex-direction: column;
}

.header__logo {
    display: flex;
    justify-content: center;
    align-items: center;
    font-family: 'Boogaloo';
}

.header__input {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 10px;
    width: 50%;
}

.header__icon {
    display: flex;
    flex-wrap: nowrap;
}
</style>