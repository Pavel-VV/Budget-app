<template>
  <div class="list-item">
    <span class="budget-comment"> {{ listItem.comment }} </span>
    <span class="budget-value"> {{ listItem.value }} </span>
    <ElButton type="danger" size="mini" @click="deleteItem(listItem.id)">Delete</ElButton>
  </div>
</template>

<script>
export default {
  name: 'BudgetListItem',
  props: {
    listItem: {
      type: Object,
      default: () => ({}),
    }
  },
  methods: {
    deleteItem(id) {
      this.$emit('deleteItemId', id) // прокидываем в компоненту budgetList id кликнутого item
    }
  }
}
</script>

<style scoped>
.list-item {
  display: flex;
  align-items: center;
  padding: 10px 15px;
}

.budget-value {
  font-weight: bold;
  margin-left: auto;
  margin-right: 20px;
}
</style>