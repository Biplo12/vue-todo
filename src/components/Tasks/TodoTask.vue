<template>
  <div
    :class="`cursor-pointer p-4 border-l-2 w-full flex flex-col gap-2 bg-white bg-opacity-5 relative ${
      task.reminder ? 'border-ming' : 'border-white'
    }`"
    @dblclick="onEnableReminder(task.id)"
  >
    <h3 class="opacity-25 text-xs">{{ formattedCreatedAt }}</h3>
    <h1 class="text-xl font-bold">{{ task.title }}</h1>
    <button class="absolute right-3 top-3 text-red-500" @click="onDelete(task.id)">
      <X />
    </button>
  </div>
</template>

<script lang="ts">
import { X } from 'lucide-vue-next'
import { format } from 'timeago.js'
import type { ITodoTask } from './../../interfaces'

export default {
  name: 'TodoTask',
  components: {
    X
  },
  props: {
    task: {
      type: Object as () => ITodoTask,
      required: true
    }
  },
  computed: {
    formattedCreatedAt(): string {
      if (this.task.createdAt instanceof Date) {
        return format(this.task.createdAt, 'en_US').toLocaleUpperCase()
      }
      return ''
    }
  },
  methods: {
    onDelete(id: number) {
      this.$emit('delete-task', id)
    },
    onEnableReminder(id: number) {
      this.$emit('enable-reminder', id)
    }
  }
}
</script>
