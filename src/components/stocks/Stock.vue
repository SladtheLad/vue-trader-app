<template>
  <div class="card w-25">
    <div class="card-header">
      <h4 class="card-title">
        {{ stock.name }}
        <small>(Price: {{ stock.price }})</small>
      </h4>
    </div>
    <div class="card-body">
      <div class="float-left">
        <input type="number" class="form-control" placeholder="Quantity" v-model.number="quantity">
      </div>
      <div class="float-right">
        <button
          class="btn btn-success"
          @click="buyStock"
          :disabled="quantity <= 0 || !Number.isInteger(quantity)"
        >Buy</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['stock'],
  data() {
    return {
      quantity: 0
    }
  },
  methods: {
    buyStock() {
      const order = {
        stockId: this.stock.id,
        stockPrice: this.stock.price,
        quantity: this.quantity
      }
      this.$store.dispatch('buyStock', order)
      this.quantity = 0
    }
  }
}
</script>
