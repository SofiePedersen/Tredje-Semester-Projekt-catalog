<script setup>
import batman from '@/assets/image/batman-comic-png.jpg';
import vildkatten from '@/assets/image/vildkatten-game-png.webp';
import catan from '@/assets/image/catan_en.webp';
import spots from '@/assets/image/spots-board-game.jpg';
import { ref, onMounted, onUnmounted } from "vue";

// const products = [
//     { image: vildkatten, name: 'Vildkatten - børneudgave', price: 'DKK 300', status: 5 },
//     { image: batman, name: 'Batman comics - fuld sæt', price: 'DKK 67', status: 2 },
//     { image: catan, name: 'Catan - brætspil', price: 'DKK 400', status: 8 },
//     { image: spots, name: 'Spots! - hunde brætspil', price: 'DKK 280', status: 1 },
//     { image: catan, name: 'Catan - brætspil', price: 'DKK 400', status: 8 },
//     { image: spots, name: 'Spots! - hunde brætspil', price: 'DKK 280', status: 1 },
//     { image: batman, name: 'Batman comics - fuld sæt', price: 'DKK 67', status: 2 },
// ]


const products = ref([])

onMounted(async () => {
  try {
    const res = await fetch('https://best-bud-db-default-rtdb.europe-west1.firebasedatabase.app/faraos/products.json');

    if (!res.ok) {
      throw new Error('Failed to fetch pets');
    }

    const data = await res.json();
    products.value = data;

  } catch (error) {
    console.error(error);
  }
});

</script>

<template>
    <div class="wrapper">
        <h2>PRODUKT KATALOG</h2>
        <div class="product-grid">
            <div class="card" v-for="(product, index) in products" :key="index">
                <img :src="product.image" :alt="product.name" />
                <h3>{{ product.name }}</h3>
                <p class="price">{{ product.price }}</p>
                <p class="status">{{ product.status }} på lager</p>
                <button class="add-btn">Tilføj</button>
            </div>
        </div>
        <a href="#" class="showmore">Fandt du ikke dét du søgte?</a><br>
        <a href="#" class="showmore">Klik her for at se mere</a>
    </div>
</template>


<style scoped lang="scss">
@import "../assets/main.scss";

.wrapper {
    background-color: $color-pharaos-gold;
    padding-left: 15rem;
    padding-right: 15rem;
    padding-bottom: 3rem;

    h2 {
        padding-top: 2.5rem;
        padding-left: 0;
        color: $color-newspaper-white;
    }

    p, h3 {
        font-family: $font-play;
    }
}

.product-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 1.5rem;
    width: 100%;
    margin-bottom: 2rem;
}

.card {
    flex: 1 1 calc(25% - 1.5rem);
    height: 500px;
    box-sizing: border-box;
    padding: 1rem;
    background: #ffffff;
    box-shadow: 0.44rem 0.44rem rgba(0, 0, 0, 0.25);
    display: flex;
    flex-direction: column;
    align-items: center;
}

.card img {
    width: 100%;
    height: 60%;
    border-radius: 0.5rem;
    margin-bottom: 1rem;
}

.card h3 {
    font-size: 1.5rem;
    margin: 0.5rem 0;
    text-align: center;
}

.price {
    font-size: 1.2rem;
    font-weight: bold;
    margin: 0.2rem 0;
}

.status {
    font-size: 0.9rem;
    color: #157915;
    margin-bottom: 1rem;
}

.add-btn {
    padding: 0.6rem 1rem;
    font-size: 1rem;
    background-color: #007bff;
    color: #fff;
    border: none;
    border-radius: 0.5rem;
    cursor: pointer;
}

.showmore {
    color: $color-anubis-black;
    font-family: $font-play;
    font-size: 1.1rem;
    text-decoration: none;
}

.showmore:last-of-type {
    text-decoration: underline;
}

.showmore:last-of-type:hover {
    color: $color-tactical-blue;
}

.add-btn:hover {
    background-color: #005fcc;
}
</style>
