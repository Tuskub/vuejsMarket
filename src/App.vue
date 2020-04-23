<template>
  <div id="app">
    <AddProduct
      @add-product = "addProduct"
    />
    <Marketplace
      v-bind:products = "products"
      @remove-product = "removeProduct"
    />
    <img alt="Vue logo" src="./assets/fetchimage.webp">
  </div>
</template>

<script>
import Marketplace from "@/components/Marketplace";
import AddProduct from "@/components/AddProduct";
export default {
  name: 'App',
  data() {
    return {
      products: [
        {id: 1, title: 'Товар 1', count: 1, price: 5050 },
        {id: 2, title: 'Товар 2', count: 2, price: 4050 },
        {id: 3, title: 'Товар 3', count: 10,price: 3050 },
        {id: 4, title: 'Товар 4', count: 11, price: 2050 }
      ]
    }
  },
  methods: {
    removeProduct(id) {
      this.products = this.products.filter(p => p.id !== id)
    },
    addProduct(newProduct) {
      this.products.push(newProduct)
    }
  },
  components: {
    Marketplace,
    AddProduct
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
