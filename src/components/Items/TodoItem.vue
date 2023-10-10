<template>
  <div class="">
    <h1>{{ item.title }}</h1>
    <p>{{ item.description }}</p>
    <h3>{{ item.createdAt.toDateString() }}</h3>
  </div>
</template>

<script lang="ts">
interface ITodoItem {
  title: string
  description: string
  createdAt: Date
  isDone: boolean
}

export default {
  name: 'TodoItem',
  props: {
    item: {
      type: Object as () => ITodoItem,
      required: true
    }
  }
}
</script>
