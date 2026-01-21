<script setup>
defineProps({
  totalPrice: Number,
})

const emit = defineEmits(['openDrawer'])
</script>

<template>
  <header
    class="flex items-center justify-between border-b border-slate-400 px-4 py-4 md:px-10 md:py-8"
  >
    <router-link to="/" class="flex items-center gap-2 md:gap-4">
      <img src="/assets/img/logo.webp" alt="Logo" class="w-6 md:w-10" width="40" height="40" />
      <h2 class="text-sm font-bold uppercase md:text-xl">phones</h2>
    </router-link>

    <ul class="flex items-center gap-4 md:gap-10">
      <li>
        <button
          @click="() => emit('openDrawer')"
          class="flex items-center gap-2 text-blue-800 hover:text-black md:gap-3"
        >
          <img src="/assets/img/cart.svg" alt="cart" width="18" height="18" />
          <span class="text-sm font-bold md:text-base">{{ totalPrice }} $</span>
        </button>
      </li>

      <li>
        <router-link
          to="/favorites"
          class="flex items-center gap-2 text-sm text-blue-800 hover:text-black md:gap-3 md:text-base"
        >
          <img src="/assets/img/heart.svg" alt="favorites" width="18" height="18" />
          <span class="max-[450px]:hidden">Favorite</span>
        </router-link>
      </li>
    </ul>
  </header>
</template>
