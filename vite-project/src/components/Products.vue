<script setup>
import {ref} from "vue";
import axios from "axios";
import Loading from "./Loading.vue"
import ProductCard from "./ProductCard.vue"

const products = ref()

const loadProducts = () => {
  axios.get(
      'https://fakestoreapi.com/products'
  )
      .then(productsResponse => {
        products.value = productsResponse.data
        console.log(productsResponse.data)
      })
}

setTimeout(loadProducts, 100)
</script>

<template>
  <loading :active="products == null"/>
  <div
      v-if="products"
      class="grid grid-cols-4 m-3"
  >
    <div
        v-for="product in products" :key="product.id"
        class="m-1 flex flex-col items-center rounded border-2 border-solid border-purple-500"
    >
      <product-card :product="product"/>
    </div>
  </div>
</template>