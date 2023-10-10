<template>
  <TodoItem v-for="item in items" :key="item.title" :item="item" />
</template>

<script lang="ts">
import TodoItem from './TodoItem.vue'

export default {
  name: 'TodoItems',
  components: {
    TodoItem
  },
  data() {
    return {
      items: [
        {
          title: 'Doctor Appointment',
          description: 'Date - 20.10.2023 | 15:35',
          isDone: true,
          createdAt: new Date()
        },
        {
          title: 'Spanish lesson',
          description: 'Date - 22.10.2023 | 11:35',
          isDone: false,
          createdAt: new Date()
        }
      ]
    }
  }
}
</script>
