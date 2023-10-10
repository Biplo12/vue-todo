<template>
  <div
    :class="`p-4 border-l-2 flex flex-col gap-2 bg-white bg-opacity-5 w-80 relative ${
      item.isDone ? 'border-green-500' : 'border-white'
    } `"
  >
    <h3 class="opacity-25 text-sm">{{ formattedCreatedAt }}</h3>
    <h1 class="text-xl font-bold">{{ item.title }}</h1>
    <p class="opacity-75">{{ item.description }}</p>
    <button class="absolute right-3 top-3 text-red-500">
      <X />
    </button>
  </div>
</template>

<script lang="ts">
import { X } from 'lucide-vue-next'
interface ITodoItem {
  title: string
  description: string
  createdAt: Date
  isDone: boolean
}

export default {
  name: 'TodoItem',
  components: {
    X
  },
  props: {
    item: {
      type: Object as () => ITodoItem,
      required: true
    }
  },
  computed: {
    formattedCreatedAt(): string {
      if (this.item.createdAt instanceof Date) {
        return this.item.createdAt.toDateString()
      }
      return ''
    }
  }
}
</script>
