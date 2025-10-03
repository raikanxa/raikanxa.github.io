<script setup lang="ts">
import { defineProps } from 'vue';

// Define props with TypeScript types
const props = defineProps<{
  label: string;
  value: number;
}>();
</script>

<template>
  <div class="text-gray-500 text-12px">
    <div class="flex justify-between text-sm mb-1">
      <span>{{ props.label }}</span>
      <span>{{ props.value }}%</span>
    </div>
    <div class="w-full h-2 px-[2px] pt-[2px] pb-2 border-[1px] border-[#C0392B] bg-[white] rounded">
      <div class="h-[5px] bg-[#C0392B] rounded" :style="{ width: `${value}%` }"></div>
    </div>
  </div>
</template>

<style scoped>
/* Scoped styles for the component */
</style>