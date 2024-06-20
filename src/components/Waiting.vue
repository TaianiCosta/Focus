<script setup lang="ts">
import type { Order } from '../types.ts'
import OrderDetails from './OrderDetails.vue'
import { ref } from 'vue'

const newOrder = ref<Order>()
const hasNewOrder = ref(false)

fetchEventSource('http://localhost:3000/stores/4/orders/new', {
  method: 'GET',
  headers: {
    Accept: 'application/json',
    'X-API-KEY': import.meta.env.X_API_KEY,
    Authorization: 'Bearer "eyJhbGci..."'
  },
  async onopen(response) {
    if (response.ok) {
      console.log('connected!')
      return // everything's good
    }
  },
  onmessage(msg) {
    if (msg.event === 'new-order') {
      let data = JSON.parse(msg.data)
      console.log(data.order)
      newOrder.value = {
        id: data.order.id,
        createdAt: new Date(data.order.created_at)
      }
      hasNewOrder.value = true
    } else {
      hasNewOrder.value = false
    }
  }
})
</script>

<template>
  <div>
    <h3>waiting orders</h3>
    <template v-if="hasNewOrder">
      <div>
        <p>new order!</p>
      </div>

      <OrderDetails :order="newOrder" />
    </template>
  </div>
</template>
