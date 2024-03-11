<template>
  <div>
    <h2>Checkout</h2>
    <div v-for="(item, index) in cartItems" :key="index" class="cart-item">
      <p>{{ item.name }}</p>
      <p>{{ item.price }}</p>
      <button @click="removeItem(index)">Remove</button>
    </div>
    <p>Total Price: {{ calculateTotalPrice() }}</p>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  props: ['cartItems'],
  methods: {
    removeItem(index) {
      this.$emit('removeItem', index)
    },
    calculateTotalPrice() {
      return this.cartItems.reduce((total, item) => total + item.price, 0)
    }
  }
}
</script>

<style>
.cart-item {
  border: 1px solid #ccc;
  padding: 10px;
  margin: 10px;
}
</style>
