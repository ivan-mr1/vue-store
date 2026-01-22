<script setup>
import axios from 'axios'
import { ref, computed, inject } from 'vue'

import DrawerHead from './DrawerHead.vue'
import CartItemList from './CartItemList.vue'
import InfoBlock from './InfoBlock.vue'

const props = defineProps({
  totalPrice: Number,
  vatPrice: Number,
})

const { cart, closeDrawer } = inject('cart')

const isCreating = ref(false)
const orderId = ref(null)

const createOrder = async () => {
  try {
    isCreating.value = true

    const { data } = await axios.post(`https://e01bc5e6df68d939.mokky.dev/orders`, {
      items: cart.value,
      totalPrice: props.totalPrice.value,
    })

    cart.value = []

    orderId.value = data.id
  } catch (err) {
    console.log(err)
  } finally {
    isCreating.value = false
  }
}

const cartIsEmpty = computed(() => cart.value.length === 0)
const buttonDisabled = computed(() => isCreating.value || cartIsEmpty.value)
</script>

<template>
  <div @click="closeDrawer" class="fixed top-0 left-0 z-10 h-full w-full bg-black opacity-70"></div>
  <div class="fixed top-0 right-0 z-20 h-full w-96 bg-white p-8">
    <DrawerHead />

    <div v-if="!totalPrice || orderId" class="flex h-full items-center">
      <InfoBlock
        v-if="!totalPrice && !orderId"
        title="The cart is empty"
        description="Add at least one product to place an order."
        image-url="/assets/img/package-icon.png"
      />
      <InfoBlock
        v-if="orderId"
        title="The order has been placed!"
        :description="`Your order #${orderId} will be handed over to courier delivery soon`"
        image-url="/assets/img/order-success-icon.png"
      />
    </div>

    <div v-else>
      <CartItemList />

      <div class="mt-7 flex flex-col gap-4">
        <div class="flex gap-2">
          <span>All price:</span>
          <div class="flex-1 border-b border-dashed"></div>
          <span class="font-bold">{{ totalPrice }} $</span>
        </div>

        <div class="flex gap-2">
          <span>Tax 5%:</span>
          <div class="flex-1 border-b border-dashed"></div>
          <span class="font-bold">{{ vatPrice }} $</span>
        </div>

        <button
          :disabled="buttonDisabled"
          @click="createOrder"
          class="mt-4 w-full cursor-pointer rounded-xl bg-lime-500 py-3 text-white transition hover:bg-lime-600 active:bg-lime-700 disabled:bg-slate-300"
        >
          Place an order
        </button>
      </div>
    </div>
  </div>
</template>
