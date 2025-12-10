<script setup>
const products = [
    { image: '#', name: 'Product 1', price: 'DKK 300', status: 5 },
    { image: '#', name: 'Product 2', price: 'DKK 67', status: 2 },
    { image: '#', name: 'Product 3', price: 'DKK 400', status: 8 },
    { image: '#', name: 'Product 4', price: 'DKK 280', status: 1 },
    { image: '#', name: 'Product 5', price: 'DKK 99', status: 12 },
    { image: '#', name: 'Product 6', price: 'DKK 125', status: 3 },
    { image: '#', name: 'Product 7', price: 'DKK 200', status: 7 },
    { image: '#', name: 'Product 8', price: 'DKK 48', status: 4 }
]
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
    </div>
</template>


<style scoped lang="scss">
@import "../assets/main.scss";

.wrapper {
    background-color: red;
    padding-left: 15rem;
    padding-right: 15rem;

    h2 {
        padding-left: 0;
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
}

.card {
    flex: 1 1 calc(25% - 1.5rem);
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
    color: #007b00;
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

.add-btn:hover {
    background-color: #005fcc;
}
</style>
