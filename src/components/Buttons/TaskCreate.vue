<template>
  <button
    class="border border-green-500 px-4 py-2 duration-150 ease-linear hover:bg-green-500 hover:text-black"
    @click="taskCreateHandler"
  >
    Create Task
  </button>
</template>

<script lang="ts">
export default {
  name: 'TaskCreate',
  components: {},
  methods: {
    taskCreateHandler() {
      console.log('create')
    }
  }
}
</script>
