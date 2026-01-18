<script setup>
import Card from './Card.vue'

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
      title="mens shoes Nice"
      :price="88"
      image-url="assets/img/sneakers/sneakers-1.jpg"
      :is-added="false"
      :is-favorite="false"
      :onClickAdd="onClickAdd"
      :onClickFavorite="onClickFavorite"
    />
  </div>
</template>
