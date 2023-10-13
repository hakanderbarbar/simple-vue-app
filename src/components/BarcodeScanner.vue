<template>
  <div>
    <vue-barcode-reader @decode="onDecode" @loaded="onLoaded"></vue-barcode-reader>
    <h2>The decoded value in QR/barcode is</h2>
    <h2>{{ decodedText }}</h2>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import { StreamBarcodeReader } from 'vue-barcode-reader';

const decodedText = ref('');

const onLoaded = () => {
  console.log('Barcode scanner loaded');
  startScanning(); // Starten Sie das Scannen, wenn der Barcode-Scanner geladen ist
};

const onDecode = (text) => {
  decodedText.value = text;
};

const startScanning = () => {
  const scanner = new StreamBarcodeReader();
  scanner.initScanner();
  scanner.startScanner();
};

onMounted(() => {
  startScanning(); // Starten Sie das Scannen, wenn die Komponente montiert ist
});
</script>
