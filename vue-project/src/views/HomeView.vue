<template>
  <div>
    <div v-for="item in items">
      <div class="item-card">
        <div class="card-title">{{ item.name }}</div>
        <img :src="item.img" alt="">
        <div class="card-description">{{ item.description }}</div>
        <button @click="addToCart(item)">Add to Cart</button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { items } from './icons/array'; 
import { ref } from 'vue'; 
const addToCart = (item) => {
  cart.value.push(item);
};
</script>