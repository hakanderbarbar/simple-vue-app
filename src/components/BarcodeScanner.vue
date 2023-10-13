<script>
import { StreamBarcodeReader } from 'vue-barcode-reader';

export default {
  components :{
    StreamBarcodeReader,
  },
  data(){
    return{
      code: undefined,
      name: undefined,
      cost: undefined
    }
  },
  methods: {
    onLoaded(){
      console.log("LOADED!!!")
    }, 
    onDecode (result) {

      this.code = result
      console.log(result)

      if(result == 4337185051937 ){
        this.name = "K-Classic Wasserflasche"
        this.cost = 0.29
      }else if(result == 90446832){
        this.name = "Red Bull"
        this.cost = 1.49
      }else if(result == 42143819){
        this.name = "Saskia Wasserflasche"
        this.cost = 0.15
      }else if(result == 90433221){
        this.name = "Red Bull Acai"
        this.cost = 1.19
      }else {
        this.name = "unbekannt"
        this.cost = "?"
      }
    }
  }
}
</script>

<template>
  <header>
    <h1>Barcode Reader App</h1>
  </header>
  <body>
    <StreamBarcodeReader @decode="onDecode" @loaded="onLoaded"></StreamBarcodeReader>
    <p>The Barcode is: {{ code }}</p>
    <p> Your product is: {{ name }}</p>
    <p>Your product costs {{ cost }}€</p>
  </body>
</template>


