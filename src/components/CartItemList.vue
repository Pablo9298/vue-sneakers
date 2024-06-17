<script setup>
import CartItem from './CartItem.vue'
import { inject } from 'vue'

const { cart, removeFromCart } = inject('cart')
</script>

<template>
  <div class="flex flex-col flex-1 gap-4 justify-between" v-auto-animate>
    <CartItem
      v-for="item in cart"
      :key="item.id"
      :id="item.id"
      :price="item.price"
      :title="item.title"
      :image-url="item.imageUrl"
      @on-click-remove="() => removeFromCart(item)"
    />
  </div>
</template>
