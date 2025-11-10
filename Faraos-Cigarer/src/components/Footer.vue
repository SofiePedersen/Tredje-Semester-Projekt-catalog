<script setup>
import FooterMenuComp from './FooterMenuComp.vue';
</script>

<template>
    <footer>
        <FooterMenuComp />
    </footer>
</template>

<style lang="scss" scoped>
@import '../assets/main.scss';

footer {
    background-color: $color-anubis-black;
    width: 100%;
}
</style>