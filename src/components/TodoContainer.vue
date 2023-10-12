<template>
  <div class="flex flex-col gap-6 justify-center items-center min-w-80">
    <h1 class="text-7xl font-bold"><span class="text-ming">Vue</span> Todo List.</h1>
    <h2>Double click on task to add it to <span class="text-ming">reminders</span>.</h2>
    <TaskCreate @add-task="addTask" />
    <TodoTasks :tasks="tasks" @enable-reminder="enableReminder" @delete-task="deleteTask" />
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
      this.tasks = this.tasks.filter((task: ITodoTask) => task.id !== id)
    },
    addTask(title: string) {
      this.tasks.unshift({
        id: this.tasks.length + 1,
        title,
        reminder: false,
        createdAt: new Date()
      })
    },
    enableReminder(id: number) {
      const index = this.tasks.findIndex((task: ITodoTask) => task.id === id)
      if (index !== -1) {
        this.tasks[index] = { ...this.tasks[index], reminder: !this.tasks[index].reminder }
      }
    }
  },
  data() {
    return {
      tasks: [] as ITodoTask[]
    }
  }
}
</script>
