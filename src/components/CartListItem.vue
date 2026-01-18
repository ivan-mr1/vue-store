<script setup>
import CartItem from './CartItem.vue'
</script>

<template>
  <div class="flex flex-1 flex-col gap-4">
    <CartItem
      title="Nike Air Max 270 Men's Sneakers"
      :price="70"
      img="/assets/img/sneakers/sneakers-10.jpg"
    />
    <CartItem
      title="Nike Air Max 270 Men's Sneakers"
      :price="70"
      img="/assets/img/sneakers/sneakers-9.jpg"
    />
  </div>
</template>
