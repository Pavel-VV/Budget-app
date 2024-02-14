<template>
  <div class="list-item">
    <span class="budget-comment"> {{ listItem.comment }} </span>
    <span class="budget-value"> {{ listItem.value }} </span>
    <ElButton type="danger" size="mini" @click="dialogVisible = true">Delete</ElButton>
    <ElDialog
      :visible.sync="dialogVisible"
      width="30%"
      :show-close = false>
      <span>Вы точно хотите удалить запись?</span>
      <span slot="footer" class="dialog-footer">
        <ElButton @click="dialogVisible = false">Отмена</ElButton>
        <ElButton type="primary" @click="deleteItem(listItem.id)">Подтвердить</ElButton>
      </span>
    </ElDialog>
  </div>
</template>

<script>
export default {
  name: 'BudgetListItem',
  data: () => ({
    dialogVisible: false,
  }),
  props: {
    listItem: {
      type: Object,
      default: () => ({}),
    }
  },
  methods: {
    deleteItem(id) {
      // if(!confirm('Вы уверены?')) return;
      this.dialogVisible = false;
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