<template>
  <div>
    <div v-for="item in cart">
      <div class="cart-item">
        <div class="item-info">
          <div>{{ item.name }}</div>
          <div>{{ item.price }}</div>
        </div>
        <button @click="removeFromCart(item)">Remove</button>
      </div>
    </div>
    <div>Total Price: {{ calculateTotalPrice() }}</div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import { computed } from 'vue';

const removeFromCart = (index) => {
  cart.value.splice(index, 1);
};

const calculateTotalPrice = computed(() => {
  return cart.value.reduce((total, item) => total + item.price, 0);
});
</script>