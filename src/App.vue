<script>
import { computed, ref, reactive, toRef, toRefs } from 'vue'

  export default {

     setup(){
      const message = ref("Hello Sohan!")

      const quantity = ref(1)

      const item = reactive({
        name: "Product 1",
        price: 10

      })
      const increment = () => quantity.value++
      const decrement = () => quantity.value--

      const swapProduct = () => {
        item.name = "Product A"
        item.price = 30

      }

      const total = computed(() => item.price * quantity.value)


    /*  const nameRef = toRef(item, 'name');
      
      console.log('nameRef:', nameRef.value);

      item.name = "New Product"

      console.log('nameRef:', nameRef.value);*/

      //const itemRefs = toRefs(item)
      const {name, price} = toRefs(item)

     /* console.log('name:', itemRefs.name.value)
      console.log('price', itemRefs.price.value)

      item.name = "Hot Product"
      item.price = 50

      console.log('name:', itemRefs.name.value)
      console.log('price', itemRefs.price.value)*/

      return {
        message,
        quantity,
        increment,
        decrement,
       // item,
        name,
        price,
        total,
        swapProduct

      }

     }
  }

</script>

<template>
  <!--  <h1>{{ item.name }} : {{item.price}}</h1> -->
  <h1>{{  name }} : {{ price}}</h1>
   <!-- <input type="text" v-model="message"> -->
   <button @click="swapProduct">Swap Product</button>
  <button @click="price++">increment Price</button>

   <h2>{{ quantity }}</h2>
   <button @click="increment">+</button> 
   <button @click="decrement">-</button>

   <h3>Total: {{ total }}</h3>

</template>

<style scoped>
</style>
