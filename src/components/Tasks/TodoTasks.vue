<template>
  <TodoTask
    v-for="task in tasks"
    :key="task.title"
    :task="task"
    @delete-task="$emit('delete-task', task.id)"
  />
</template>

<script lang="ts">
import type { ITodoTask } from '../../interfaces'
import TodoTask from './TodoTask.vue'

export default {
  name: 'TodoTasks',
  props: {
    tasks: Array as () => ITodoTask[]
  },
  components: {
    TodoTask
  },
  emits: ['delete-task']
}
</script>
