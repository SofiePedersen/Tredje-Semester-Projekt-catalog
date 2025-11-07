<script setup>

</script>

<template>
    <footer>
        <div class="footer-lists">
            <div class="footer-lists--toggle">
                <h3>Butikker</h3>
                <ikon></ikon>
            </div>
            <ul>
                <li>
                    <RouterLink to="/">Åbningstider</RouterLink>
                </li>
                <li>
                    <RouterLink to="/">Lokationer</RouterLink>
                </li>
                <li>
                    <RouterLink to="/">Faraos Cigarer Online</RouterLink>
                </li>
                <li>
                    <RouterLink to="/">Aktiviteter</RouterLink>
                </li>
                <li>
                    <RouterLink to="/">Kalender</RouterLink>
                </li>
            </ul>
        </div>
    </footer>
</template>

<style lang="scss" scoped>
@import '../assets/main.scss';

footer {
    background-color: $color-anubis-black;
    width: 100%;

    .footer-lists {

        .footer-lists--toggle {
            display: flex;
            background-color: red;
        }

        h3 {
            font-family: $font-boogaloo;
            color: $color-newspaper-white;
        }
    }
}
</style>