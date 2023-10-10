<template>
  <div class="flex justify-center items-center gap-2 w-full">
    <div
      class="w-full flex justify-center items-center gap-2 border-black border rounded-md bg-white bg-opacity-5 py-1 px-3"
    >
      <input class="w-full !outline-none bg-transparent" placeholder="Add a task..." />
      <button>
        <PlusCircle class="text-green-500 w-5 h-5" />
      </button>
    </div>
  </div>
</template>

<script lang="ts">
import { PlusCircle } from 'lucide-vue-next'

export default {
  name: 'TaskCreate',
  components: { PlusCircle },
  methods: {
    taskCreateHandler() {
      console.log('create')
    }
  }
}
</script>
