<script setup>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { faAngleDown } from '@fortawesome/free-solid-svg-icons';



const storeMapSections = [
  {
    title: "JYLLAND",
    items: [
      { text: "AARHUS GAMES", link: "#" },
      { text: "AARHUS COMICS", link: "#" },
    ]
  },
  {
    title: "FYN",
    items: [
      { text: "ODENSE", link: "#" },
    ]
  },
  {
    title: "SJÆLLAND",
    items: [
      { text: "KØBENHAVN COMICS & POTTER", link: "#" },
      { text: "KØBENHAVN BRÆT- & ROLLESPIL", link: "#" },
      { text: "KØBENHAVN FIGURSPIL", link: "#" },
      { text: "KØBENHAVN KORTSPIL", link: "#" },
      { text: "KØBENHAVN MANGA", link: "#" },
      { text: "KØBENHAVN UDKLÆDNING & LIVEROLLESPIL", link: "#" },
      { text: "KØBENHAVN MERCHANDISE", link: "#" },
      { text: "LYNGBY GAMES", link: "#" },
      { text: "LYNGBY COMICS", link: "#" },
    ]
  },
];

</script>


<template>
  <img class="butikker__kort" src="@/assets/image/Landekort.webp" alt="Landkort" />
  <h2>HVOR VIL DU HEN?</h2>

  <div class="butikker__danmark">
    <div>
      <h2 class="butikker__landsdele">JYLLAND
      <FontAwesomeIcon :icon="faAngleDown" class="butikker__ikon" /> 
      </h2>
    </div>

    <h2 class="butikker__landsdele">FYN
      <FontAwesomeIcon :icon="faAngleDown" class="butikker__ikon" /> 
    </h2>
    <h2 class="butikker__landsdele">SJÆLLAND 
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
  justify-content: space-between;
  padding: 1rem;  
  margin-bottom: 2rem;  
  border: none;
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
