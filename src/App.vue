<script setup>
import Header from './components/Header.vue';
import BarcodeScanner from './components/BarcodeScanner.vue';

</script>

<template>
  <header>
    
  </header>

    <div class="web-site-header">
      <Header></Header>
    </div>

  <main class="container">

    <BarcodeScanner/>    

  </main>
</template>

<style scoped>
.container {
  overflow: hidden;
}
.container-item {
  display: flex;
}

.web-site-header {
  position: sticky;
  top: sticky;
  top: 0;
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
