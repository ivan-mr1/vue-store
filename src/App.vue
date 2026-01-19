<script setup>
import Header from './components/Header.vue'
import CardList from './components/CardList.vue'
// import Drawer from './components/Drawer.vue'

const items = [
  {
    id: 1,
    title: 'Men Sneakers Nike Blazer Mid Suede',
    price: 12999,
    imageUrl: '/assets/img/sneakers/sneakers-1.jpg',
  },
  {
    id: 2,
    title: 'Men Sneakers Nike Air Max 270',
    price: 15600,
    imageUrl: '/assets/img/sneakers/sneakers-2.jpg',
  },
  {
    id: 3,
    title: 'Men Sneakers Nike Blazer Mid Suede',
    price: 8499,
    imageUrl: '/assets/img/sneakers/sneakers-3.jpg',
  },
  {
    id: 4,
    title: 'Sneakers Puma X Aka Boku Future Rider',
    price: 7800,
    imageUrl: '/assets/img/sneakers/sneakers-4.jpg',
  },
  {
    id: 5,
    title: 'Sneakers Future Rider',
    price: 9550,
    imageUrl: '/assets/img/sneakers/sneakers-5.jpg',
  },
  {
    id: 6,
    title: 'Sneakers Black Edition',
    price: 16999,
    imageUrl: '/assets/img/sneakers/sneakers-6.jpg',
  },
  {
    id: 7,
    title: 'Sneakers Orange Boomb Edition',
    price: 7499,
    imageUrl: '/assets/img/sneakers/sneakers-7.jpg',
  },
  {
    id: 8,
    title: 'Sneakers Nike Air Max 270',
    price: 15600,
    imageUrl: '/assets/img/sneakers/sneakers-8.jpg',
  },
  {
    id: 9,
    title: 'Sneakers Nike Air Force 1',
    price: 5900,
    imageUrl: '/assets/img/sneakers/sneakers-9.jpg',
  },
  {
    id: 10,
    title: 'Sneakers Adidas Ultraboost',
    price: 11500,
    imageUrl: '/assets/img/sneakers/sneakers-10.jpg',
  },
  {
    id: 11,
    title: 'Sneakers Puma Clyde All-Pro',
    price: 7600,
    imageUrl: '/assets/img/sneakers/sneakers-11.jpg',
  },
  {
    id: 12,
    title: 'Sneakers Converse Chuck Taylor All-Star',
    price: 13000,
    imageUrl: '/assets/img/sneakers/sneakers-12.jpg',
  },
]
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
              <img src="/assets/img/search.svg" />
            </div>
          </div>
        </div>
      </div>
      <CardList :items="items" />
    </div>
  </div>
</template>
