<template>
  <div class="bg-sooty text-white w-full h-screen flex justify-center items-center">
    <TodoContainer />
    <RouterView />
  </div>
</template>

<script setup lang="ts">
import { RouterView } from 'vue-router'
import TodoContainer from './components/TodoContainer.vue'
</script>
