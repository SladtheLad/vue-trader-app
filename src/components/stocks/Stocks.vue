<template>
  <div class="card-deck">
    <app-stock v-for="stock in stocks" :key="stock" :stock="stock"></app-stock>
  </div>
</template>

<script>
import Stock from './Stock.vue'

export default {
  data() {
    return { 
      stocks: [
        { id: 1, name: 'BMW', price: 200},
        { id: 2, name: 'Google', price: 500},
        { id: 3, name: 'Apple', price: 450},
        { id: 4, name: 'Twitter', price: 300},
      ]
    }
  },
  components: {
    appStock: Stock
  }
}
</script>

<style>
.row {
  margin-top: 10px;
}
</style>

