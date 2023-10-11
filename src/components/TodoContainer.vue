<template>
  <div class="flex flex-col gap-6 justify-center items-center min-w-80">
    <h1 class="text-3xl font-bold">Todo List</h1>
    <TaskCreate @add-task="addTask" />
    <TodoTasks :tasks="tasks" @delete-task="deleteTask" />
  </div>
</template>

<script lang="ts">
import TodoTasks from './Tasks/TodoTasks.vue'
import TaskCreate from './Buttons/TaskCreate.vue'
import type { ITodoTask } from './../interfaces'
export default {
  name: 'TodoContainer',
  components: {
    TaskCreate,
    TodoTasks
  },
  methods: {
    deleteTask(id: number) {
      this.tasks = this.tasks.filter((item: ITodoTask) => item.id !== id)
    },
    addTask(title: string) {
      this.tasks.unshift({
        id: this.tasks.length + 1,
        title,
        reminder: false,
        createdAt: new Date()
      })
    }
  },
  data() {
    return {
      tasks: [] as ITodoTask[]
    }
  }
}
</script>
