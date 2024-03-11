<template>
  <div>
    <h2>Apple Products</h2>
    <div class="items-container">
      <div v-for="item in items" :key="item.name" class="card">
        <img :src="item.image" alt="item.name" />
        <p>{{ item.name }}</p>
        <p>{{ item.price }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          name: "iPhone 15 Pro",
          description: "6.7-inch OLED display, A17 Bionic chip, triple-lens camera system",
          price: 1099,
          image: 'iphone15pro.jpg'
        },
        {
          name: "iPhone 15",
          description: "6.1-inch Liquid Retina HD display, A17 Bionic chip, dual-lens camera system",
          price: 899,
          image: 'iphone15.jpg'
        },
        {
          name: "iPhone SE (3rd Gen)",
          description: "4.7-inch Retina HD display, A15 Bionic chip, single-lens rear camera",
          price: 429,
          image: 'iphonese.jpg'
        },
        // Add more Apple items here
      ]
    };
  }
};
</script>

<style>
.items-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.card {
  border: 1px solid #ccc;
  padding: 10px;
  margin: 10px;
}
</style>