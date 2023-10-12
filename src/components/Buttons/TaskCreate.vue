<template>
  <form
    class="flex justify-between w-72 items-center gap-2 border-black border rounded-md bg-white bg-opacity-5 py-1 px-3"
    @submit.prevent="onAdd"
  >
    <input
      class="w-full !outline-none bg-transparent"
      placeholder="Add a task..."
      @change="(e) => onTitleChange(e)"
      maxlength="32"
      :value="title"
    />
    <button @click="onAdd" class="text-ming">
      <PlusCircle class="w-5 h-5" />
    </button>
  </form>
</template>

<script lang="ts">
import { PlusCircle } from 'lucide-vue-next'

export default {
  name: 'TaskCreate',
  components: { PlusCircle },
  data() {
    return {
      title: '' as string
    }
  },
  methods: {
    onTitleChange(e: Event) {
      e.preventDefault()
      this.title = (e.target as HTMLInputElement).value
    },
    onAdd() {
      if (this.title !== '') {
        this.$emit('add-task', this.title)
        this.title = ''
      }
    }
  },
  emits: ['add-task']
}
</script>
