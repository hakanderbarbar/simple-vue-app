<template>
  <div>
    <h1>Barcode Scanner</h1>
    <button @click="showMessage">Zeige Nachricht</button>
    <p>Barcode-Wert: {{ scannedBarcodeValue }}</p>
  </div>
</template>

<script>
export default {
  name: 'DisplayBarcodesList',

  data() {
    return {
      barcodeData: [
        { code: '12345', value: 42 },
        { code: '67890', value: 99 },
        // Weitere Einträge für verschiedene Barcodes und Werte
      ],
      scannedBarcode: '', // Hier wird der gescannte Barcode-Wert "code" gespeichert
      scannedBarcodeValue: null, // Hier wird der zugehörige Wert "value" gespeichert
    };
  },

  methods: {
    showMessage() {
      if (this.scannedBarcode) {
        // Suche nach dem gescannten Barcode in der Datenliste
        const barcodeEntry = this.barcodeData.find(
          (entry) => entry.code === this.scannedBarcode
        );

        if (barcodeEntry) {
          this.scannedBarcodeValue = barcodeEntry.value;
        } else {
          this.scannedBarcodeValue = 'Barcode nicht gefunden';
        }
      } else {
        this.scannedBarcodeValue = 'Kein Barcode gescannt';
      }
    },
  },

  created() {
    console.log('Component created');
  },
};
</script>

<style scoped>
/* Your component-specific CSS styles go here */
</style>
