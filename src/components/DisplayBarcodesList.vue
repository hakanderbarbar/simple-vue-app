<template>
    <div>
      <!-- Your component's template here -->
      <h1>{{ message }}</h1>
    </div>
  </template>
  
  <script>
  export default {
    name: 'MyComponent', // Replace 'MyComponent' with your component name
  
    data() {
      return {
        message: 'Hello, Vue 3!', // Your data properties go here
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
  </style>
  
  