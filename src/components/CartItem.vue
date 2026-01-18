<script setup>
defineProps({
  title: String,
  img: String,
  price: Number,
  cartItemClick: Function,
})
</script>
<template>
  <div class="relative flex w-full gap-4 rounded-xl border border-slate-100 p-4">
    <img :src="img" class="h-16 w-16" alt="Sneaker" width="70" height="70" loading="lazy" />
    <div class="flex w-full flex-col">
      <h3>{{ title }}</h3>
      <div class="mt-5 flex justify-between">
        <span class="font-bold">{{ price }} $</span>
        <img
          @click="cartItemClick"
          class="cursor-pointer opacity-30 transition hover:opacity-100"
          src="/assets/img/close.svg"
          alt="Close"
          width="32"
          height="32"
          loading="lazy"
        />
      </div>
    </div>
  </div>
</template>
