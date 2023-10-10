<template>
  <div>
    <TodoItem v-for="item in items" :key="item.title" :item="item" />
  </div>
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
          title: 'one',
          description: 'first task',
          isDone: false,
          createdAt: new Date()
        }
      ]
    }
  }
}
</script>
