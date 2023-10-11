<template>
  <div class="flex justify-center items-center gap-2 w-full">
    <div
      class="w-full flex justify-center items-center gap-2 border-black border rounded-md bg-white bg-opacity-5 py-1 px-3"
    >
      <input
        class="w-full !outline-none bg-transparent"
        placeholder="Add a task..."
        @change="(e) => onTitleChange(e)"
        maxlength="32"
      />
      <PlusCircle class="text-green-500 w-5 h-5 cursor-pointer" @click="onAdd" />
    </div>
  </div>
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
    onTitleChange(event: InputEvent) {
      this.title = (event.target as HTMLInputElement).value
    },
    onAdd() {
      this.$emit('add-task', this.title)
    }
  },
  emits: ['add-task']
}
</script>
