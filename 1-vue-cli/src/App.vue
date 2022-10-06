<template>
  <div class="container">

    <!--<myComp/>-->
    <div class="cart">
      <h3>Sepet</h3>
      <ul>
        <li  v-for="item in cartItems " :key="item.id" >{{ item.title }}</li>
      </ul>
      <p v-if="cartItems.length == 0">sepetiniz boş alışverişe başlayın</p>
    </div>
    <Product @addToCart="cartItems.push($event)" :product="product" v-for="product in productList" :key="product.id"/>


  </div>
</template>

<script>

import Product from "@/components/Product";
export default {
  components : {
    Product,


  },
  data() {
    return {
      productList: [
        {
          id: 1,
          title: "MacBook Pro",
          price: 100,
          count: 0,
          description:"Açıklama 1"
        },
        {
          id: 2,
          title: "İphone",
          price: 50,
          count: 100,
          description:"Açıklama 2"
        },
        {
          id: 3,
          title: "Klavye",
          price: 10,
          count:1000,
          description:"Açıklama 3"
        }
      ],
      cartItems : []
    }
  }

}
</script>

<style>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.cart {
  margin-bottom: 50px;
  text-align: center;
}
.cart ul li {
  list-style: none;
}
</style>