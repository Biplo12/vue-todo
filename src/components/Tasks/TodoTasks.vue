<template>
  <div class="w-64 flex flex-col gap-3 justify-center items-center">
    <TodoTask
      v-for="task in tasks"
      :key="task.title"
      :task="task"
      @delete-task="$emit('delete-task', task.id)"
      @enable-reminder="$emit('enable-reminder', task.id)"
    />
    <p v-if="tasks?.length === 0">Add some tasks!</p>
  </div>
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
  emits: ['delete-task', 'enable-reminder']
}
</script>
