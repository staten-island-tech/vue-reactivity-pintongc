<template>
    <div class="dest-card">
      <img :src="destination.img" :alt="destination.name" />
      <h3>{{ destination.name }}</h3>
      <p>Price: ${{ destination.price }}</p>
      <button @click="addToCart">Add to Cart</button>
    </div>
  </template>
  
  <script setup>
  import { defineProps } from 'vue';
  
  const props = defineProps({
    destination: Object,
    addToCart: Function  // Ensure addToCart is defined as a prop
  });
  
  function addToCart() {
    // Call the addToCart method passed from the parent component
    props.addToCart(props.destination);
  }
  </script>
  
  <style scoped>
  .dest-card {
    padding: 10px;
    width: 200px;
    align-items: center;
  }
  
  .dest-card img {
    width: 100%;
  }
  
  .dest-card button {
    margin-top: 10px;
  }
  </style>