<template>
  <div class="flex flex-col gap-6">
    <h1 class="text-3xl font-bold">Todo List</h1>
    <TodoItems />
    <TaskCreate />
  </div>
</template>

<script lang="ts">
import TodoItems from './Items/TodoItems.vue'
import TaskCreate from './Buttons/TaskCreate.vue'
export default {
  name: 'TodoContainer',
  components: {
    TaskCreate,
    TodoItems
  }
}
</script>
