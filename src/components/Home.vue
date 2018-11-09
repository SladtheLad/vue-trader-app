<template>
  <div>
    <h1>Trade or "Vue" your Portfolio</h1>
    <h6 class="small-text">Save & and Load your Data</h6>
    <br>
    <h6 class="small-text">Go to Stocks for the available companies and buy, or go to Portfolio to see what you have and Sell!</h6>
    <br>
    <h6 class="small-text">Click on 'End Day' to begin a new day of Trading!</h6>
    <hr>
    <p>Your current Funds: {{ funds | currency }}</p>
  </div>
</template>

<script>
export default {
  computed: {
    funds() {
      return this.$store.getters.funds
    }
  }
}
</script>




