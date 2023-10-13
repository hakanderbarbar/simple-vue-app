<template>
    <div class="headstyle">
      <!-- Your component's template here -->
      <h1>{{ message }}</h1>
      <p> {{ text }} </p>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Header', // Replace 'MyComponent' with your component name
  
    data() {
      return {
        message: 'Barcode Scanner', // Your data properties go here
        text: 'Please scan your Barcode using the Camera',
      };
    },
  
    // You can define methods here
    methods: {
      // Example method
      showMessage() {
        alert(this.message);
      },
    },
  
    // You can also define computed properties
    computed: {
      // Example computed property
      reversedMessage() {
        return this.message.split('').reverse().join('');
      },
    },
  
    // You can add lifecycle hooks like created, mounted, etc.
    created() {
      console.log('Component created');
    },
  };
  
  </script>
  
  <style scoped>
  /* Your component-specific CSS styles go here */
  .headstyle {
    text-align: center;
  }
  </style>
  
  