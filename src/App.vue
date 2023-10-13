<script setup>
import Header from './components/Header.vue';
import DisplayBarcodesList from './components/DisplayBarcodesList.vue';
import BarcodeScanner from './components/BarcodeScanner.vue';

</script>

<template>
  <header>
    <div>
      <Header></Header>
    </div>
  </header>

  <main class="container">
    <BarcodeScanner class="container-item" />
    <DisplayBarcodesList class="container-item" />
  </main>
</template>

<style scoped>
.container {
  overflow: hidden;
}
.container-item {
  display: flex;
}
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
