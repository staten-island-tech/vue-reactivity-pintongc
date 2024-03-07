<script setup>
import { items } from './icons/array'; 
import { ref } from 'vue';
const cart = ref([]);
const addToCart = (item) => {
  cart.value.push(item);
};
</script>

<template>
    <div v-for="item in items">
      <div class="card-title">{{ item.name }}</div>
      <img :src="item.img" alt="">
      <div class="card-description">{{ item.description }}</div>
      <button @click="addToCart(item)">Add to Cart</button>
    </div>
</template>