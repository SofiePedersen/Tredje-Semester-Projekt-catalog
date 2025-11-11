<script setup>
import { ref } from 'vue'

const isExpanded = ref(false)
</script>

<template>
    <div class="roar-image">
        <img src="#" />
    </div>
    <div class="about-section">
        <h2>BUTIKKEN I ODENSE</h2>
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
</template>

<style lang="scss" scoped></style>