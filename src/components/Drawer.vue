<script setup>
import CartListItem from './CartListItem.vue'
import DrawerHead from './DrawerHead.vue'
</script>

<template>
  <div class="fixed top-0 left-0 z-10 h-full w-full bg-black opacity-70"></div>
  <div class="fixed top-0 right-0 z-20 h-full w-96 bg-white p-8">
    <DrawerHead />
    <CartListItem />

    <div class="mt-7 mb-6 flex flex-col gap-4">
      <div class="flex gap-2">
        <span>All price:</span>
        <div class="flex-1 border-b border-dashed"></div>
        <span class="font-bold">1290 $</span>
      </div>
      <div class="flex gap-2">
        <span>Tax 5%</span>
        <div class="flex-1 border-b border-dashed"></div>
        <span class="font-bold">290 $</span>
      </div>
      <button
        disabled=""
        class="mt-4 w-full cursor-pointer rounded-xl bg-lime-500 py-3 text-white transition hover:bg-lime-600 active:bg-lime-700 disabled:bg-slate-400"
      >
        Place an order
      </button>
    </div>
  </div>
</template>
