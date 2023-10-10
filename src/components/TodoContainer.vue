<template>
  <div class="flex flex-col gap-6">
    <h1 class="text-3xl font-bold">Todo List</h1>
    <TodoItems />
    <div class="flex gap-3">
      <TaskCreate />
      <TaskDelete />
    </div>
  </div>
</template>

<script lang="ts">
import TodoItems from './Items/TodoItems.vue'
import TaskCreate from './Buttons/TaskCreate.vue'
import TaskDelete from './Buttons/TaskDelete.vue'
export default {
  name: 'TodoContainer',
  components: {
    TaskCreate,
    TaskDelete,
    TodoItems
  }
}
</script>
