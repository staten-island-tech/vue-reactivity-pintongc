<template>
  <div>
    <h2 class="header">Apple Store</h2>
    <div class="gallery">
      <div v-for="item in items" :key="item.item" class="card">
        <p class="card-title">{{ item.item }}</p>
        <p class="card-description">
          {{ item.description }} <br />
          Price: $ {{ item.price }}
        </p>
        <img :src="item.image" alt="item.name" />
        <button @click="addToCart(item)">Add to Cart</button>
      </div>
    </div>
  </div>
  <div class="cart">
    <h2>Shopping Cart</h2>
    <ul>
      <li v-for="item in cartItems" :key="item.id">
        {{ item.name }} - ${{ item.price }}
        <button @click="removeFromCart(item)">Remove</button>
      </li>
    </ul>
    <div>Total Price: ${{ calculateTotalPrice() }}</div>
  </div>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link
    href="https://fonts.googleapis.com/css2?family=Merriweather&display=swap"
    rel="stylesheet"
  />
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          item: 'iPhone 15 Pro',
          description: '6.7-inch OLED display, A17 Bionic chip, triple-lens camera system',
          price: 1099,
          image:
            'https://t-mobile.scene7.com/is/image/Tmusprod/Apple-iPhone-15-Pro-Blue-Titanium-frontimage'
        },
        {
          item: 'iPhone 15',
          description:
            '6.1-inch Liquid Retina HD display, A17 Bionic chip, dual-lens camera system',
          price: 899,
          image:
            'https://cdn.tmobile.com/content/dam/t-mobile/en-p/cell-phones/apple/Apple-iPhone-15/Pink/Apple-iPhone-15-Pink-frontimage.png'
        },
        {
          item: 'iPhone SE (3rd Gen)',
          description: '4.7-inch Retina HD display, A15 Bionic chip, single-lens rear camera',
          price: 429,
          image: 'https://m.media-amazon.com/images/I/61-MT8AQAPL._AC_UF894,1000_QL80_.jpg'
        },
        {
          item: 'iPad Air (5th Gen)',
          description: '10.9-inch Liquid Retina display, M1 chip, 12MP Ultra Wide camera',
          price: 599,
          image:
            'https://store.storeimages.cdn-apple.com/4982/as-images.apple.com/is/ipad-comp-air-202210?wid=338&hei=386&fmt=jpeg&qlt=90&.v=1664411153129'
        },
        {
          item: 'iPad Pro (12.9-inch, M2 chip)',
          description:
            '12.9-inch Liquid Retina XDR display, M2 chip, dual-lens rear camera with LiDAR scanner',
          price: 1099,
          image:
            'https://store.storeimages.cdn-apple.com/4982/as-images.apple.com/is/ipad-comp-pro-202210?wid=338&hei=386&fmt=jpeg&qlt=90&.v=1664411153112'
        },
        {
          item: 'MacBook Air (M2 chip, 13.6-inch)',
          description: '13.6-inch Liquid Retina display, M2 chip, 8-core CPU, 8-core GPU',
          price: 1199,
          image:
            'https://www.apple.com/v/macbook-air/r/images/overview/performance/compare/model_mba_m2__cfrbip6c05yq_large.jpg'
        },
        {
          item: 'MacBook Pro (14-inch, M1 Pro chip)',
          description: '14.2-inch Liquid Retina XDR display, M1 Pro chip, 10-core CPU, 16-core GPU',
          price: 2499,
          image:
            'https://www.apple.com/v/macbook-pro/ak/images/overview/contrast/product_tile_mbp_14_16__br3iijc0eys2_large.png'
        },
        {
          item: 'Apple Watch Ultra (Cellular)',
          description:
            '49mm titanium case, cellular connectivity, advanced fitness tracking features',
          price: 799,
          image:
            'https://store.storeimages.cdn-apple.com/4982/as-images.apple.com/is/MT5N3ref_VW_34FR+watch-49-titanium-ultra2_VW_34FR+watch-face-49-alpine-ultra2_VW_34FR?wid=750&hei=712&trim=1%2C0&fmt=p-jpg&qlt=95&.v=1694507270905'
        },
        {
          item: 'AirPods Pro (2nd Gen)',
          description:
            'Active noise cancellation, Transparency mode, Adaptive EQ, improved sound quality',
          price: 249,
          image: 'https://m.media-amazon.com/images/I/51OoKCakCfL._AC_UF350,350_QL80_.jpg'
        }
      ],
      cartItems: []
    }
  },
  methods: {
    addToCart(item) {
      const id = this.cartItems.length + 1
      const newItem = { id, name: item.item, price: item.price }
      this.cartItems.push(newItem)
    },
    removeFromCart(item) {
      this.cartItems = this.cartItems.filter((cartItem) => cartItem.id !== item.id)
    },
    calculateTotalPrice() {
      return this.cartItems.reduce((total, item) => total + item.price, 0)
    }
  }
}
</script>

<style>
.gallery {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  padding: 0px;
  width: 100vw;
  margin: 0px;
}

.card {
  background-color: white;
  border: 0.3rem solid black;
  border-radius: 30px;
  width: 20vw;
  height: 58vh;
  padding: 0%;
  margin: 1rem;
  align-items: center;
  transition: all 0.3s;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  box-shadow: 0.3rem 0.3rem 0.2rem rgb(21, 22, 22);
  overflow: hidden;
  font-size: 1rem;
}

.card-description {
  font-size: 1rem;
  text-align: center;
  margin: 0.5rem 1rem;
}

.header {
  font-size: 3rem;
}

img {
  max-width: 80%;
  max-height: 70%;
  border-radius: 15px;
  object-fit: cover;
  margin-bottom: 1px;
}

.header {
  text-align: center;
  font-size: 2rem;
  color: #333;
}

.card-title {
  font-weight: bold;
  font-size: 1.5rem;
}

.cart {
  margin-top: 20px;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

button {
  background-color: #007bff;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 5px;
  cursor: pointer;
  margin-top: 10px;
}

button:hover {
  background-color: #0056b3;
}

.header {
  font-size: 60px;
  text-align: center;
  border-bottom: black solid 3px;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 9rem;
}
</style>
