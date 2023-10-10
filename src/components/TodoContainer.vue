<template>
  <div class="flex flex-col gap-6 justify-center items-center w-80">
    <h1 class="text-3xl font-bold">Todo List</h1>
    <TaskCreate />
    <TodoTasks :tasks="tasks" @delete-task="deleteTaskHandler" />
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
    deleteTaskHandler(id: number) {
      this.tasks = this.tasks.filter((item: ITodoTask) => item.id !== id)
    }
  },
  data() {
    return {
      tasks: [
        {
          id: 1,
          title: 'Doctor Appointment',
          reminder: true,
          createdAt: new Date()
        },
        {
          id: 2,
          title: 'Spanish lesson',
          reminder: false,
          createdAt: new Date()
        }
      ]
    }
  }
}
</script>
