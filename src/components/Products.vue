<template>
  <div>
    <h1 class="title"> Products </h1>
      <p> {{ length }} products </p>
      <table class="table is-striped">
        <thead>
          <tr>
            <td>Name</td>
            <td>Description</td>
            <td>Price</td>
            <td></td>
          </tr>
        </thead>
        <tbody>
          <tr v-for="product in products" :key="product.id" track-by="id">
            <td>{{ product.name }}</td>
            <td>{{ product.description }}</td>
            <td>${{ product.price }}</td>
            <td> <button @click='addToCart(product)' class="button is-info">Add to cart</button> </td>
          </tr>
        </tbody>
      </table>
  </div>
</template>

<script>
import { mapGetters, mapActions } from 'vuex'

export default {
  name: 'app',
  computed: mapGetters({
    products: 'allProducts',
    length: 'getNumberOfProducts'
  }),
  methods: mapActions([
    'addToCart'
  ])
}
</script>


<style lang="scss">

</style>
