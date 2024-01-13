<script setup>
import CartItem from './components/CartItem.vue';
import useCart from './useCart';

const {items, addItem, removeItem } = useCart()

   addItem({
    id: 1,
    name: "Product XS",
    price: 20,
    quantity: 1

   })

</script>

<template>
  <div>
    <CartItem v-for="item in items" :cart-item="item" :key="item.id" @remove="removeItem"/>
  </div>
</template>

<style scoped>
  /* Add your styles here if needed */
</style>
