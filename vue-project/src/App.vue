<template>
  <div>
    <HomeView :items="items" />
    <CheckoutView :cart="cart" />
  </div>
</template>

<script setup>
import { items } from './icons/array'; 
import { ref } from 'vue'; 

const cart = ref([]);
</script>