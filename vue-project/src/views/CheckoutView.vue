<template>
    <div class="checkout">
      <h1>This is a checkout page</h1>
      <div>Total:</div>
      <div class="payment">Select payment methods</div>
      <div class="items-table">
        <div class="item">
          <div class="delete-btn"></div>
          <div class="quantity"></div>
          <div class="desc"></div>
          <div class="title"></div>
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
  