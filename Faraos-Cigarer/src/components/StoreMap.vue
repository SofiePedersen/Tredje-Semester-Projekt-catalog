<script setup>



</script>


<template>
  <img class="butikker__kort" src="@/assets/image/Landekort.webp" alt="Landkort" />
  <h2>HVOR VIL DU HEN?</h2>

  <div class="butikker__danmark">
    <h2 class="butikker__landsdele">Jylland</h2>
    <p>Find alle de lokale butikker på Jylland her:</p>

    <h2 class="butikker__landsdele">Fyn</h2>
    <h2 class="butikker__landsdele">Sjælland</h2>
  </div>

</template>

<style lang="scss" scoped>

.butikker__kort {
  width: 100%;
  height: auto;
}

.butikker__danmark {
  display: flex;
  justify-content: space-around;
  flex-direction: column;
  margin-top: 2rem;
  $font-boogaloo: 'Boogaloo';
  font-size: 28px;
  gap: 1rem;
  padding: 1rem 0;
  margin-left: 15%;
  margin-right: 15%;
}

.butikker__landsdele {
  background-color:#0E0F11;
  padding: 1rem;
  margin-bottom: 2rem;  
}

</style>
