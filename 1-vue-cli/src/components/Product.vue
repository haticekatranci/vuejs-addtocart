<template>
  <div class="products">
     <strong>{{ product.title }}</strong>
     <h4> {{ product.description }}</h4>
     <strong> Fiyat ={{ product.price }} </strong><br>
     <strong>Adet = {{ product.count }}</strong><br>
     <button @click="addToCart(product)" >Sepete Ekle</button>
  </div>
</template>

<script>

export default {
  props : ["product"],
  methods : {
    addToCart(product) {
      this.$emit("addToCart", product )
    }
  }
}
</script>

<style>
.products {
  border: 2px dashed #666;
  padding: 10px ;
  width: 300px;
  margin-bottom: 5px;

}
.products:hover{
  border:2px solid #666;
  transition: 5s all ;
}
</style>