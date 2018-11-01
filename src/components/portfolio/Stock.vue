<template>
    <div class="card w-25">
      <div class="card-header">
        <h4 class="card-title">
          {{ stock.name }}
          <small>(Price: {{ stock.price }} | Quantity: {{ stock.quantity }})</small>
        </h4>
      </div>
      <div class="card-body">
        <div class="float-left">
          <input
            type="number"
            class="form-control"
            placeholder="Quantity"
            v-model.number="quantity"
          >
        </div>
        <div class="float-right">
          <button
            class="btn btn-success"
            @click="sellStock"
            :disabled="quantity <= 0 || !Number.isInteger(quantity)"
          >Sell</button>
        </div>
      </div>
    </div>
</template>

<script>
import { mapActions } from 'vuex'

export default {
  props: ['stock'],
  data() {
    return {
      quantity: 0
    }
  },
  methods: {
    ...mapActions({
      sellBackStock: 'sellStock'
    }),
    sellStock() {
      const order = {
        stockId: this.stock.id,
        stockPrice: this.stock.price,
        quantity: this.quantity
      }
      this.sellBackStock(order)
      this.quantity = 0
    }
  }
}
</script>
