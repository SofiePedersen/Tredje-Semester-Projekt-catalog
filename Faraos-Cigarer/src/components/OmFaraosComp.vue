<script setup>
    import { ref } from 'vue'

    const isExpanded = ref(false)
</script>

<template>
    <div class="about-section">
        <h2>LIDT OM FARAOS</h2>
        <div class="about-content">
            <!-- Dynamic class binding -->
            <p :class="{ collapsed: !isExpanded }">
                Vi er landets største specialbutik for alt fra tegneserier og brætspil til manga og merchandise.
                <br><br>
                Du finder os i København, Aarhus, Odense og Lyngby – med i alt ni butikker, hvor hver afdeling har sine
                egne specialister klar til at hjælpe dig, uanset om du er til superhelte, samlekort, figurer eller
                fantasy-universer.
                <br><br>
                I København har vi dedikerede butikker til hver kategori, mens Lyngby og Aarhus samler det hele under ét
                tag. Vores 600 m² store butik i Odense har alt det bedste fra Faraos Cigarer – samlet ét sted.
                <br><br>
                Det hele findes også her på hjemmesiden – og alt hvad du ser online, er på lager i vores butikker i
                København (og omvendt).
                <br><br>
                Har du spørgsmål, står vores passionerede medarbejdere altid klar med råd og vejledning – både i
                butikken og online.
            </p>
            <button class="read-more-btn" @click="isExpanded = !isExpanded">
                <!-- Her bruger vi en ternary operator som lader os skrive en if else statement i vores abstraction -->
                <!-- Basically hvis isExpanded er true vis "læs mindre", hvis false vis "læs mere" -->
                {{ isExpanded ? 'Læs mindre' : 'Læs Mere' }}
            </button>
        </div>
    </div>
    <div class="roar-image">
        <img src="../assets/image/faraos-cigarer-roar.png" />
    </div>
</template>

<style lang="scss" scoped>
@import '../assets/main.scss';

.about-section {
    margin-top: 3rem;
    padding: 2rem;
    padding-top: 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background-color: $color-pharaos-gold;
}

.about-content {
    position: relative;
}

.about-section h2 {
    color: white;
}

.about-content p {
    transition: max-height 0.3s ease;
    overflow: hidden;
}

.about-content p.collapsed {
    max-height: 6rem;
    position: relative;
}

.read-more-btn {
    background: none;
    border: none;
    color: #3396E6;
    cursor: pointer;
    padding: 0;
    font-size: inherit;
    margin-top: 0.5rem;
}

.read-more-btn:hover {
    color: #a8d1f3;
}

.roar-image {
    background-color: $color-pharaos-gold;
    padding: 2rem;
    padding-top: 0rem;
    display: flex;
    justify-content: center;
}

.roar-image img {
    display: block;
    height: auto;
    max-width: 100%;
}

p, button {
  font-family: $font-play;
}

</style>