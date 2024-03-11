<template>
  <div id="app">
    <router-link class="home-btn" to="/">Home </router-link>
    <router-link class="checkout=btn" to="/checkout">Checkout</router-link>
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  text-align: center;
  font-size: 2rem;
}
</style>
