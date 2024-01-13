<script>
import { ref } from 'vue';
import CartItem from './components/CartItem.vue';
import useCart from './useCart';

export default {
  components: { CartItem },
  setup() {
   const {items, addItem, removeItem } = useCart()

   addItem({
    id: 1,
    name: "Product XS",
    price: 20,
    quantity: 1

   })
 


    return { items, removeItem };
  }
}
</script>

<template>
  <div>
    <CartItem v-for="item in items" :cart-item="item" :key="item.id" @remove="removeItem"/>
  </div>
</template>

<style scoped>
  /* Add your styles here if needed */
</style>
