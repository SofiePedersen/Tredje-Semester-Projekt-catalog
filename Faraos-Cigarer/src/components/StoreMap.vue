<script setup>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { faAngleDown } from '@fortawesome/free-solid-svg-icons';


</script>


<template>
  <img class="butikker__kort" src="@/assets/image/Landekort.webp" alt="Landkort" />
  <h2>HVOR VIL DU HEN?</h2>

  <div class="butikker__danmark">
    <div>
      <h2 class="butikker__landsdele">Jylland
      <FontAwesomeIcon :icon="faAngleDown" class="butikker__ikon" />
      </h2>
    </div>

    <p>Find alle de lokale butikker på Jylland her:</p>

    <h2 class="butikker__landsdele">Fyn
      <FontAwesomeIcon :icon="faAngleDown" class="butikker__ikon" />
    </h2>
    <h2 class="butikker__landsdele">Sjælland
      <FontAwesomeIcon :icon="faAngleDown" class="butikker__ikon" />
    </h2>
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
  display: flex;
  background-color:#0E0F11;
  justify-content: start;
  padding: 1rem;  
  margin-bottom: 2rem;  
}

.butikker__ikon {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: .5rem;
  background: none;
  border: none;
  color: #efd17a;
  font-size: 28px;
  cursor: pointer;
}


</style>
