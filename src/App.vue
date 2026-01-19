<script setup>
import { onMounted, ref } from 'vue'
import axios from 'axios'
import Header from './components/Header.vue'
import CardList from './components/CardList.vue'

// import Drawer from './components/Drawer.vue'

const items = ref([])

// onMounted(() => {
//   fetch('https://e01bc5e6df68d939.mokky.dev/items')
//     .then((res) => res.json())
//     .then((data) => {
//       console.log(data)
//     })
// })

onMounted(async () => {
  try {
    const { data } = await axios.get('https://e01bc5e6df68d939.mokky.dev/items')
    items.value = data
  } catch (e) {
    console.log(e)
  }
})
</script>

<template>
  <!-- <Drawer /> -->
  <div class="shadow-grey-200 m-auto mt-20 w-3/5 rounded-xl bg-white shadow-xl">
    <Header />
    <div class="p-10">
      <div class="flex justify-between">
        <h1 class="mb-8 text-3xl font-bold">All products</h1>

        <div class="flex items-center gap-4">
          <select
            class="rounded-md border border-gray-200 px-3 py-2 focus:border-gray-400 focus:outline-none"
          >
            <option value="name">By name</option>
            <option value="price">By price (cheap)</option>
            <option value="price">By price (expensive)</option>
          </select>
          <div class="relative">
            <input
              type="text"
              class="rounded-md border border-gray-200 py-2 pr-4 pl-10 focus:border-gray-400 focus:outline-none"
              placeholder="Search..."
            />
            <div class="pointer-events-none absolute inset-y-0 left-0 flex items-center pl-3">
              <img src="/assets/img/search.svg" alt="search" width="16" height="16" />
            </div>
          </div>
        </div>
      </div>
      <div class="mt-10">
        <CardList :items="items" />
      </div>
    </div>
  </div>
</template>
