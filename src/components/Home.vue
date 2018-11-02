<template>
  <div>
    <h1>Trade or Vue your Portfolio</h1>
    <h6>Save & and Load your Data</h6>
    <h6>Click on 'End Day' to begin a new day of Trading!</h6>
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

