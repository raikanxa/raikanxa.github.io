<script setup lang="ts">
import { defineProps } from 'vue';

// Define props with TypeScript types
const props = defineProps<{
  label: string;
  value: number;
}>();
</script>

<template>
  <div>
    <div class="flex justify-between text-sm mb-1">
      <span>{{ label }}</span>
      <span>{{ value }}%</span>
    </div>
    <div class="w-full h-1.5 bg-gray-200 rounded">
      <div class="h-1.5 bg-red-400 rounded" :style="{ width: `${value}%` }"></div>
    </div>
  </div>
</template>

<style scoped>
/* Scoped styles for the component */
</style>