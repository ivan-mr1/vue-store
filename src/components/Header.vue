<script setup>
defineProps({
  totalPrice: Number,
})

const emit = defineEmits(['openDrawer'])
</script>

<template>
  <header class="flex justify-between border-b border-slate-200 px-10 py-8">
    <router-link to="/"
      ><div class="flex items-center gap-4">
        <img src="/assets/img/logo.webp" alt="Logo" class="w-10" width="40" height="40" />
        <div>
          <h2 class="text-xl font-bold uppercase">phones</h2>
        </div>
      </div>
    </router-link>

    <ul class="flex items-center gap-10">
      <li
        @click="() => emit('openDrawer')"
        class="flex cursor-pointer items-center gap-3 text-gray-500 hover:text-black"
      >
        <img src="/assets/img/cart.svg" alt="Image" width="18" height="18" />
        <b>{{ totalPrice }} $</b>
      </li>

      <router-link to="/favorites">
        <li class="flex cursor-pointer items-center gap-3 text-gray-500 hover:text-black">
          <img src="/assets/img/heart.svg" alt="Image" width="18" height="18" />
          <span>Favorite</span>
        </li>
      </router-link>

      <li class="flex cursor-pointer items-center gap-3 text-gray-500 hover:text-black">
        <img src="/assets/img/profile.svg" alt="Image" width="18" height="18" />
        <span>User</span>
      </li>
    </ul>
  </header>
</template>
