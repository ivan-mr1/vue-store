<script setup>
const emit = defineEmits(['onClickRemove'])

defineProps({
  id: Number,
  title: String,
  imageUrl: String,
  price: Number,
})
</script>
<template>
  <div class="flex items-center gap-4 rounded-xl border border-slate-200 p-4">
    <img class="h-16 w-16" :src="imageUrl" :alt="title" width="70" height="70" loading="lazy" />

    <div class="flex flex-1 flex-col">
      <h3>{{ title }}</h3>

      <div class="mt-2 flex justify-between">
        <span class="flex-1 font-bold">{{ price }} $</span>
        <img
          @click="emit('onClickRemove')"
          class="cursor-pointer opacity-40 transition hover:opacity-100"
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
