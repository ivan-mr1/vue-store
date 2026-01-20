<script setup>
import { ref, onMounted } from 'vue'
import axios from 'axios'

import CardList from '../components/CardList.vue'

const favorites = ref([])

onMounted(async () => {
  try {
    const { data } = await axios.get(
      'https://e01bc5e6df68d939.mokky.dev/favorites?_relations=items',
    )

    favorites.value = data.map((obj) => obj.item)
  } catch (err) {
    console.log(err)
  }
})
</script>

<template>
  <h2 class="mb-8 text-3xl font-bold">My favorite</h2>

  <CardList :items="favorites" is-favorites />
</template>
