<script setup>
import MyBar from "./components/MyBar.vue";
import MyCard from "./components/MyCard.vue";
import items from "./attractions.json";
</script>

<template>
  <header>
    <MyBar />
  </header>

  <main>
    <h1>Attractions</h1>
    <div className="grid-container">
      <MyCard v-for="item in items" v-bind="item" />
    </div>
  </main>
</template>

<style scoped>
h1 {
  padding-left: 10px;
}

.grid-container {
  display: grid;
  grid-column-gap: 0.5rem;
  grid-row-gap: 0.5rem;
}
@media (min-width: 576px) {
  .grid-container {
    grid-template-columns: repeat(1, 1fr);
  }
}
@media (min-width: 992px) {
  .grid-container {
    grid-template-columns: repeat(3, 1fr);
  }
}

h1::first-letter {
  color: rgb(112, 248, 141);
  font-size: 50px;
}

h1:hover {
  color: dodgerblue;
}
</style>
