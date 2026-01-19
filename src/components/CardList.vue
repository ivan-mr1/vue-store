<script setup>
import Card from './Card.vue'

defineProps({
  items: Array,
})

const onClickAdd = () => {
  alert('add')
}

const onClickFavorite = () => {
  alert('add to favorites')
}
</script>

<template>
  <div class="grid grid-cols-4 gap-5">
    <Card
      v-for="item in items"
      :key="item.id"
      :title="item.title"
      :price="item.price"
      :image-url="item.imageUrl"
      :is-added="false"
      :is-favorite="false"
      :onClickAdd="onClickAdd"
      :onClickFavorite="onClickFavorite"
    />
  </div>
</template>
