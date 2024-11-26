<script setup>
defineProps(['product'])
</script>

<template>
  <img class="max-h-28" :src="product.image" :alt="product.image">
  <p class="mx-3">{{ product.title }}</p>
  <p class="mx-3"><b>Price:</b> ${{ product.price }}</p>
  <span class="rounded bg-green-200 w-40 text-center hover:bg-green-600">
    <button >Add to cart</button>
  </span>
</template>