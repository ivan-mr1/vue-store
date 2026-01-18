<script setup>
import Header from './components/Header.vue'
import CardList from './components/CardList.vue'
import Drawer from './components/Drawer.vue'
</script>

<template>
  <Drawer />
  <div class="shadow-grey-200 m-auto mt-20 w-3/5 rounded-xl bg-white shadow-xl">
    <Header />
    <div class="p-10">
      <h1 class="mb-8 text-3xl font-bold">All products</h1>
      <CardList />
    </div>
  </div>
</template>
