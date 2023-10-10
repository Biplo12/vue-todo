<template>
  <button
    class="border border-red-500 px-4 py-2 duration-150 ease-linear hover:bg-red-500"
    @click="taskDeleteHandler"
  >
    Delete Task
  </button>
</template>

<script lang="ts">
export default {
  name: 'TaskDelete',
  components: {},
  methods: {
    taskDeleteHandler() {
      console.log('delete')
    }
  }
}
</script>
