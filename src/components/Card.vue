<script setup>
defineProps({
  title: String,
  imageUrl: String,
  price: Number,
  isFavorite: Boolean,
  isAdded: Boolean,
  onClickAdd: Function,
  onClickFavorite: Function,
})
</script>

<template>
  <article
    class="relative flex w-full cursor-pointer flex-col rounded-xl border border-slate-100 p-8 transition hover:-translate-y-2 hover:transform hover:shadow-xl"
  >
    <img
      @click="onClickFavorite"
      :src="!isFavorite ? '/assets/img/like-1.svg' : '/assets/img/like-2.svg'"
      alt="add to Favorite"
      class="absolute top-8 left-8"
      width="32"
      height="32"
      loading="lazy"
    />
    <img :src="imageUrl" alt="product" class="w-full" width="133" height="112" loading="lazy" />
    <h3>{{ title }}</h3>
    <div class="flex justify-between">
      <div class="mt-5 flex flex-col">
        <span class="text-slate-400">Price:</span>
        <span class="font-bold">{{ price }} $.</span>
      </div>
      <img
        @click="onClickAdd"
        :src="!isAdded ? '/assets/img/plus.svg' : '/assets/img/checked.svg'"
        alt="add to cart"
        class=""
        width="32"
        height="32"
        loading="lazy"
      />
    </div>
  </article>
</template>
