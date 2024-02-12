<template>
  <div class="total-value">Total Balance: {{total}} </div>
</template>

<script>
export default {
  name: "TotalBalance",
  props: {
    total: {
      type: Number,
      default: 0,
    },
  },
}

</script>

<style scoped>
.total-value {
  padding: 20px;
  font-size: 26px;
  text-transform: uppercase;
  text-align: center;
}

</style>
