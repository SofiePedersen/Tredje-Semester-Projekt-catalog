<script setup>

</script>

<template>
    <nav class="breadcrumbs">
        <RouterLink class="breadcrumbs__text" to="/">Forside</RouterLink>
        <p class="breadcrumbs__text">></p>
        <RouterLink class="breadcrumbs__text" to="/Butikker">Butikker</RouterLink>
        <p class="breadcrumbs__text">></p>
        <RouterLink class="breadcrumbs__text" to="/Information">Odense</RouterLink>
    </nav>

    <div class="map-container">
        <img class="gMap" src="../assets/image/faraos-local-map.webp" alt="billede af det google maps over Faraos Cigarers lokale butik i odense" />
    </div>
</template>

<style lang="scss" scoped>
@import '../assets/main.scss';

.breadcrumbs {
    display: flex;
    justify-content: flex-start;

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
    color: #3396E6;
}

.map-container{
    padding: 2rem;

    .gMap {
        width: 100%;
        height: auto;
    }
}

</style>
