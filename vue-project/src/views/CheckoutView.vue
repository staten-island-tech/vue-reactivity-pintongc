<template>
    <div class="checkout">
      <h1>This is a checkout page</h1>
      <div>Total:</div>
      <div class="payment">Select payment methods</div>
      <div class="items-table">
        <div class="item">
          <div class="delete-btn"><button @click="" class="delete-btn">Delete</button></div>
          <div class="quantity">5x</div>
          <div class="desc">Brief item description</div>
          <div class="title">Item</div>
          <div class="item-img"><img src="" alt="" srcset=""></div>
          <list-item></list-item>
        </div>
      </div>
    </div>
  </template>
  
  <style>
  @media (min-width: 1024px) {
    .cart {
      min-height: 100vh;
      display: flex;
      align-items: center;
    }
    html {
      font-size: xx-large;
    }
    h1 {
      font-size: xx-large;
    }
  }
  </style>
  
  <script>
  
createList({
components: {
  ListItem
},
  setup() {
    
  }
})


  </script>